# Java 中的 ShortBuffer compact()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-compact-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-compact-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。缓冲区的当前位置与其限制(如果有)之间的短路被复制到缓冲区的开头。也就是说，索引 p =位置()处的短路被复制到索引 0，索引 p + 1 处的短路被复制到索引 1，以此类推，直到索引极限()–1 处的短路被复制到索引 n =极限()–1–p。然后，缓冲区的位置被设置为 n+1，其极限被设置为其容量。如果定义了标记，则会将其丢弃。缓冲区的位置被设置为复制的短路数，而不是零，因此调用此方法后可以立即调用另一个相对 put 方法。

**语法**:

```java
public abstract ShortBuffer compact()
```

**返回值**:该方法返回与该缓冲区内容相同的**新短缓冲区**。

**异常**:如果这个缓冲区是只读的，这个方法抛出**readonlybufferenexception**。

下面的程序说明了**紧凑()**的方法:

**程序 1** :

```java
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer

        // creating object of shortbuffer
        // and allocating size capacity
        ShortBuffer sb = ShortBuffer.allocate(capacity);

        // putting the value in shortbuffer
        sb.put((short)856);
        sb.put((short)961);
        sb.put((short)54);

        // print the ShortBuffer
        System.out.println("Original ShortBuffer: "
                           + Arrays.toString(sb.array()));

        System.out.println("Position: " + sb.position());

        System.out.println("limit: " + sb.limit());

        // Creating a compacted ShortBuffer of same ShortBuffer
        // using compact() method
        ShortBuffer shortBuffer = sb.compact();

        // print the ShortBuffer
        System.out.println("\nCompacted ShortBuffer: "
                           + Arrays.toString(shortBuffer.array()));

        System.out.println("Position: " + shortBuffer.position());

        System.out.println("limit: " + shortBuffer.limit());

        // putting the value in compacted shortbuffer
        shortBuffer.put((short)961);

        // print the ShortBuffer
        System.out.println("\nUpdated Compacted ShortBuffer: "
                           + Arrays.toString(shortBuffer.array()));
        System.out.println("Position: " + shortBuffer.position());
        System.out.println("limit: " + shortBuffer.limit());
    }
}
```

**Output:**

```java
Original ShortBuffer: [856, 961, 54, 0, 0, 0, 0, 0, 0, 0]
Position: 3
limit: 10

Compacted ShortBuffer: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
Position: 7
limit: 10

Updated Compacted ShortBuffer: [0, 0, 0, 0, 0, 0, 0, 961, 0, 0]
Position: 8
limit: 10

```

**程序 2:** 演示 ReadOnlyBufferException。

```java
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of ShortBuffer
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity);

            // putting the value in floatbuffer
            sb.put((short)856);
            sb.put((short)961);
            sb.put((short)6010);
            sb.rewind();

            // Creating a read-only copy of ShortBuffer
            // using asReadOnlyBuffer() method
            ShortBuffer sb1 = sb.asReadOnlyBuffer();

            // print the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer ShortBuffer: ");
            while (sb1.hasRemaining())
                System.out.print(sb1.get() + ", ");
            System.out.println("");

            // print the Position of ShortBuffer sb
            System.out.println("\nPosition: " + sb.position());

            // print the Limit of ShortBuffer fb
            System.out.println("\nlimit: " + sb.limit());

            // Creating a compacted ShortBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer sb1");

            ShortBuffer floatBuffer = sb1.compact();
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws " + e);
        }
    }
}
```

**Output:**

```java
ReadOnlyBuffer ShortBuffer: 856, 961, 6010, 0, 0, 0, 0, 0, 0, 0, 

Position: 0

limit: 10

Trying to compact the ReadOnlyBuffer sb1
Exception throws java.nio.ReadOnlyBufferException

```
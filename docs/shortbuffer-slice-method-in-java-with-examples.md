# Java 中的 ShortBuffer slice()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-slice-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-slice-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的 **slice()** 方法用于创建一个新的短缓冲区，其内容是该缓冲区内容的共享子序列。

新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。
新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的短路数量，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法**:

```
public abstract ShortBuffer slice()
```

**返回值**:该方法返回**新的短缓冲区。**

以下是说明**切片()**方法的示例:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// slice() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity);

            // putting the value in Shortbuffer
            sb1.put((short)856);
            sb1.put((short)961);

            // print the ShortBuffer
            System.out.println("Original ShortBuffer: "
                               + Arrays.toString(sb1.array()));

            // print the ShortBuffer position
            System.out.println("\nposition: " + sb1.position());

            // print the ShortBuffer capacity
            System.out.println("\ncapacity: " + sb1.capacity());

            // Creating a shared subsequence buffer of given ShortBuffer
            // using slice() method
            ShortBuffer sb2 = sb1.slice();

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence ShortBuffer: "
                               + Arrays.toString(sb2.array()));

            // print the ShortBuffer position
            System.out.println("\nposition: " + sb2.position());

            // print the ShortBuffer capacity
            System.out.println("\ncapacity: " + sb2.capacity());
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output**

```
Original ShortBuffer: [856, 961, 0, 0, 0, 0, 0, 0, 0, 0]

position: 2

capacity: 10

shared subsequence ShortBuffer: [856, 961, 0, 0, 0, 0, 0, 0, 0, 0]

position: 0

capacity: 8
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// slice() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity);

            // putting the value in Shortbuffer
            sb1.put((short)856);
            sb1.put((short)961);
            sb1.put((short)656);
            sb1.put((short)361);

            // print the ShortBuffer
            System.out.println("Original ShortBuffer: "
                               + Arrays.toString(sb1.array()));

            // print the ShortBuffer position
            System.out.println("\nposition: " + sb1.position());

            // print the ShortBuffer capacity
            System.out.println("\ncapacity: " + sb1.capacity());

            // Creating a shared subsequence buffer of given ShortBuffer
            // using slice() method
            ShortBuffer sb2 = sb1.slice();
            sb2.put((short)234);
            sb2.put((short)634);

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence ShortBuffer: "
                               + Arrays.toString(sb2.array()));

            // print the ShortBuffer position
            System.out.println("\nposition: " + sb2.position());

            // print the ShortBuffer capacity
            System.out.println("\ncapacity: " + sb2.capacity());
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output**

```
Original ShortBuffer: [856, 961, 656, 361, 0, 0, 0, 0, 0, 0]

position: 4

capacity: 10

shared subsequence ShortBuffer: [856, 961, 656, 361, 234, 634, 0, 0, 0, 0]

position: 2

capacity: 6
```
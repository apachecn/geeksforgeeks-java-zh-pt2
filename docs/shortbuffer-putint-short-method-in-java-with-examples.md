# Java 中的 ShortBuffer put(int，short)方法示例

> 原文:[https://www . geesforgeks . org/short buffer-putint-short-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-putint-short-method-in-java-with-examples/)

Java . nio . short buffer 类的 **put()** 方法用于在给定的索引处将给定的短消息写入该缓冲区。

**语法**:

```java
public abstract ShortBuffer put(int index, short s)
```

**参数**:

*   **索引**:该参数指定写入做空的索引。它是可选的。
*   **s** :该参数指定要写入的短数值

**返回值**:该方法返回该**缓冲区**。

例外:

*   **indexout of Boundsexception**–如果索引为负或不小于缓冲区的限制。
*   **只读缓冲区异常**–如果该缓冲区是只读的

下面程序说明了**放()**的方法:

**程序 1** :

```java
// Java program to demonstrate put() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 3;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer
            // and allocating size capacity
            ShortBuffer sb
                = ShortBuffer.allocate(capacity);

            // putting the value in shortbuffer
            // using put() at index 0
            sb.put(0, (short)400);

            // putting the value in shortbuffer
            // using put() at index 2
            sb.put(2, (short)1000);

            // putting the value in shortbuffer
            // using put() at index 1
            sb.put(1, (short)30);

            // rewinding the shortbuffer
            sb.rewind();

            // print the ShortBuffer
            System.out.println("Original ShortBuffer: "
                               + Arrays.toString(sb.array()));
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("Exception throws: " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```java
Original ShortBuffer: [400, 30, 1000]

```

**程序 2** :
演示 IndexOutOfBoundsException。

```java
// Java program to demonstrate put() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 3;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer
            // and allocating size capacity
            ShortBuffer sb
                = ShortBuffer.allocate(capacity);

            // putting the value in shortbuffer
            // using put() at index 0
            sb.put(0, (short)31);

            // putting the value in shortbuffer
            // using put() at index 2
            sb.put(2, (short)49);

            // putting the value in shortbuffer
            // using put() at index -1
            System.out.println("Trying to put the value"
                               + " at the negative index");
            sb.put(-1, (short)27);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("Exception throws: " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```java
Trying to put the value at the negative index
Exception throws: java.lang.IndexOutOfBoundsException

```

**程序 3** :演示 ReadOnlyBufferException。

```java
// Java program to demonstrate put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 3;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer
            // and allocating size capacity
            // using allocate() method
            ShortBuffer sb
                = ShortBuffer.allocate(capacity);

            // Creating a read-only copy of ShortBuffer
            // using asReadOnlyBuffer() method
            ShortBuffer sb1 = sb.asReadOnlyBuffer();

            System.out.println("Trying to put the float value"
                               + " in read only buffer");

            // putting the value in readonly shortbuffer
            // using put() method
            sb1.put(0, (short)13);
        }

        catch (BufferOverflowException e) {

            System.out.println("Exception throws: " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```java
Trying to put the float value in read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # put-int-short-](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#put-int-short-)
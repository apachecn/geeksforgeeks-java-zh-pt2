# Java 中的 ShortBuffer 数组()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-array-in-Java-method-with-examples/](https://www.geeksforgeeks.org/shortbuffer-array-method-in-java-with-examples/)

**java.nio.ShortBuffer** 的**数组()**方法用于返回支持该缓冲区的短数组(可选)。
修改该缓冲区的内容将导致返回数组的内容被修改，反之亦然。
在调用这个方法之前调用 hasArray 方法，以确保这个缓冲区有一个可访问的后备数组。

**语法**:

```java
public final short[] array()
```

**参数**:该方法不取任何参数。

**返回值**:该方法返回备份缓冲区的数组。

例外:

*   **readonlybufferenexception**，如果缓冲区由数组支持但为只读
*   **不支持操作异常，**如果此缓冲区没有可访问的阵列支持

<
下面的程序说明了**数组()**方法的使用:

**程序 1** :

```java
// Java program to demonstrate
// array() method

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
            ShortBuffer sb = ShortBuffer.allocate(capacity);

            // putting the value in Shortbuffer
            sb.put((short)856);
            sb.put(2, (short)9);
            sb.rewind();

            // getting array from fb ShortBuffer using array() method
            short[] sbb = sb.array();

            // printing the ShortBuffer fb
            System.out.println("ShortBuffer: "
                               + Arrays.toString(sbb));
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

**Output:**

```java
ShortBuffer: [856, 0, 9, 0, 0, 0, 0, 0, 0, 0]

```

**程序 2** :显示 ReadOnlyBufferException

```java
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the sb
        int capacity1 = 10;

        // Declaring the capacity of the sb1
        int capacity2 = 5;

        // Creating the ShortBuffer
        try {
            //
            // sb
            //
            // creating object of Shortbuffer sb
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity1);

            // putting the value in sb
            sb.put((short)96);
            sb.put(2, (short)7);
            sb.put(3, (short)41);
            sb.rewind();

            // print the ShortBuffer
            System.out.println("ShortBuffer sb: "
                               + Arrays.toString(sb.array()));

            //
            // sb1
            //
            // creating object of Shortbuffer sb1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity2);

            // putting the value in sb1
            sb1.put(1, (short)445);
            sb1.put(2, (short)64);
            sb1.rewind();

            // print the ShortBuffer
            System.out.println("\nShortBuffer sb1: "
                               + Arrays.toString(sb1.array()));

            // Creating a read-only copy of ShortBuffer
            // using asReadOnlyBuffer() method
            ShortBuffer readOnlysb = sb.asReadOnlyBuffer();

            // print the ShortBuffer
            System.out.print("\nReadOnlyBuffer ShortBuffer: ");

            while (readOnlysb.hasRemaining())
                System.out.print(readOnlysb.get() + ", ");

            // try to change readOnlysb
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlysb for editing");

            short[] sbarr = readOnlysb.array();
        }
        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
ShortBuffer sb: [96, 0, 7, 41, 0, 0, 0, 0, 0, 0]

ShortBuffer sb1: [0, 445, 64, 0, 0]

ReadOnlyBuffer ShortBuffer: 96, 0, 7, 41, 0, 0, 0, 0, 0, 0, 

Trying to get the array from ReadOnlysb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```
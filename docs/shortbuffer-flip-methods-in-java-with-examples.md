# Java 中的 ShortBuffer flip()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-flip-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-flip-methods-in-java-with-examples/)

**[java.nio.ShortBuffer 类](https://www.geeksforgeeks.org/tag/java-shortbuffer/)** 的 **flip()** 方法用来翻转这个缓冲区。通过翻转该缓冲区，这意味着缓冲区将被修剪到当前位置，然后该位置将被更改为零。在此过程中，如果缓冲区上有任何标记，则该标记将被自动丢弃。

**语法:**

```java
public final ShortBuffer flip()
```

**返回值:**该方法返回翻转的**短缓冲区**实例。

下面是一些示例来说明 flip()方法:

**示例 1:**

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize
        // the short array
        short[] db
            = { 10, 20, 30 };

        // wrap the short array
        // into ShortBuffer
        // using wrap() method
        ShortBuffer shortBuffer
            = ShortBuffer.wrap(db);

        // set position at index 1
        shortBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());

        // Flip the Buffer
        // using flip() method
        shortBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before flip: [10, 20, 30]
Position: 1
Limit: 3

Buffer after flip: [10, 20, 30]
Position: 0
Limit: 1

```

**示例 2:**

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // defining and allocating ShortBuffer
        // using allocate() method
        ShortBuffer shortBuffer
            = ShortBuffer.allocate(4);

        // put short value in ShortBuffer
        // using put() method
        shortBuffer.put((short)20);
        shortBuffer.put((short)345);

        // set position at index 1
        shortBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());

        // Flip the Buffer
        // using flip() method
        shortBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before flip: [20, 345, 0, 0]
Position: 1
Limit: 4

Buffer after flip: [20, 345, 0, 0]
Position: 0
Limit: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # flip–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#flip--)
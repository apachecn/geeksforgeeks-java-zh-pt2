# Java 中的 ShortBuffer rewind()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-rewind-in-Java-method-with-examples/](https://www.geeksforgeeks.org/shortbuffer-rewind-method-in-java-with-examples/)

[java.nio.ShortBuffer 类](https://www.geeksforgeeks.org/tag/java-shortbuffer/)的**倒带()**方法用来倒带这个缓冲区。通过倒带此缓冲区，采取以下操作:

*   The current position is set to zero.
*   The tag is discarded (if any), but the tag value remains unchanged.

**语法:**

```
public ShortBuffer rewind()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个**缓冲区**。

以下是说明 rewind()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ShortBuffer
        // using allocate() method
        ShortBuffer shortBuffer
            = ShortBuffer.allocate(4);

        // put short value in shortBuffer
        // using put() method
        shortBuffer.put((short)10);
        shortBuffer.put((short)20);

        // print the short buffer
        System.out.println(
            "Buffer before operation: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        shortBuffer.rewind();

        // print the shortbuffer
        System.out.println(
            "\nBuffer after operation: "
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

```
Buffer before operation: [10, 20, 0, 0]
Position: 2
Limit: 4

Buffer after operation: [10, 20, 0, 0]
Position: 0
Limit: 4

```

**示例 2:**

```
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ShortBuffer
        // using allocate() method
        ShortBuffer shortBuffer
            = ShortBuffer.allocate(5);

        // put short value in shortBuffer
        // using put() method
        shortBuffer.put((short)10);
        shortBuffer.put((short)20);
        shortBuffer.put((short)30);

        // mark will be going to discarded by rewind()
        shortBuffer.mark();

        // print the buffer
        System.out.println(
            "Buffer before operation: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        shortBuffer.rewind();

        // print the buffer
        System.out.println(
            "\nBuffer after operation: "
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

```
Buffer before operation: [10, 20, 30, 0, 0]
Position: 3
Limit: 5

Buffer after operation: [10, 20, 30, 0, 0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#rewind--)
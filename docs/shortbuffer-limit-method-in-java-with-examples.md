# Java 中的 ShortBuffer limit()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-limit-in-Java-method-with-examples/](https://www.geeksforgeeks.org/shortbuffer-limit-method-in-java-with-examples/)

[java.nio.ShortBuffer 类](https://www.geeksforgeeks.org/tag/java-shortbuffer/)的 **limit()** 方法用于修改这个 ShortBuffer 的限制。此方法将待设置的限制作为参数，并将其设置为此缓冲区的新限制。如果此缓冲区的标记已经定义，并且大于新的指定限制，则不会设置和丢弃此新限制。

**语法:**

```
public final ShortBuffer limit(int newLimit)
```

**参数:**该方法接受一个参数**新限制**，这是限制的新整数值。

**返回值:**该方法将指定的新限制设置为该缓冲区的新限制后，返回该**缓冲区**。

以下是举例说明 limit()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// limit() method

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
        shortBuffer.put((short)30);

        // print the short buffer
        System.out.println(
            "ShortBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());

        // Limit the shortBuffer
        // using limit() method
        shortBuffer.limit(1);

        // print the short buffer
        System.out.println(
            "\nShortBuffer after "
            + "setting buffer's limit: "
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
ShortBuffer before setting buffer's limit: [20, 30, 0, 0]
Position: 2
Limit: 4

ShortBuffer after setting buffer's limit: [20, 30, 0, 0]
Position: 1
Limit: 1

```

**示例 2:**

```
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ShortBuffer
        // using allocate() method
        ShortBuffer shortBuffer
            = ShortBuffer.allocate(5);

        // put short value in ShortBuffer
        // using put() method
        shortBuffer.put((short)20);
        shortBuffer.put((short)30);
        shortBuffer.put((short)40);

        // mark will be going to
        // discarded by limit()
        shortBuffer.mark();

        // print the short buffer
        System.out.println(
            "ShortBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  shortBuffer.array())
            + "\nPosition: "
            + shortBuffer.position()
            + "\nLimit: "
            + shortBuffer.limit());

        // Limit the shortBuffer
        // using limit() method
        shortBuffer.limit(4);

        // print the short buffer
        System.out.println(
            "\nShortBuffer before "
            + "setting buffer's limit: "
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
ShortBuffer before setting buffer's limit: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

ShortBuffer before setting buffer's limit: [20, 30, 40, 0, 0]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#mark--)
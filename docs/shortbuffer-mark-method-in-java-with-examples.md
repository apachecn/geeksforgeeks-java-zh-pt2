# Java 中的 ShortBuffer mark()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-mark-in-Java-method-with-examples/](https://www.geeksforgeeks.org/shortbuffer-mark-method-in-java-with-examples/)

[java.nio.ShortBuffer 类](https://www.geeksforgeeks.org/tag/java-shortbuffer/)的**标记()**方法用于将该 ShortBuffer 的当前位置标记为该缓冲区的标记。

**语法:**

```
public ShortBuffer mark()
```

**参数:**此方法不接受任何参数。

**返回值:**在当前位置设置缓冲区标记后，该方法返回该短缓冲区。

下面是说明 mark()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// mark() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            short[] darr = { 10, 20, 30, 40 };

            // creating object of ShortBuffer
            // and allocating size capacity
            ShortBuffer db = ShortBuffer.wrap(darr);

            // try to set the position at index 2
            db.position(2);

            // Set this buffer mark position
            // using mark() method
            db.mark();

            // try to set the position at index 4
            db.position(4);

            // display position
            System.out.println("position before reset: "
                               + db.position());

            // try to call reset() to restore
            // to the position we marked
            db.reset();

            // display position
            System.out.println("position after reset: "
                               + db.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("New position "
                               + "is less than "
                               + "the position "
                               + "marked before ");
            System.out.println("Exception throws: "
                               + e);
        }
    }
}
```

**输出:**

```
position before reset: 4
position after reset: 2

```

**示例 2:** 演示无效标记异常

```
// Java program to demonstrate
// mark() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            short[] darr = { 10, 20, 30, 40 };

            // creating object of ShortBuffer
            // and allocating size capacity
            ShortBuffer db = ShortBuffer.wrap(darr);

            // try to set the position at index 2
            db.position(2);

            // Set this buffer mark position
            // using mark() method
            db.mark();

            // try to set the position at index 1
            db.position(1);

            // display position
            System.out.println("position before reset: "
                               + db.position());

            // try to call reset() to restore
            // to the position we marked
            db.reset();

            // display position
            System.out.println("position after reset: "
                               + db.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("\nNew position "
                               + "is less than "
                               + "the position "
                               + "marked before ");
            System.out.println("Exception throws: "
                               + e);
        }
    }
}
```

**输出:**

```
position before reset: 1

New position is less than the position marked before 
Exception throws: java.nio.InvalidMarkException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#mark--)
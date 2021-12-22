# Java 中的 ShortBuffer clear()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-clear-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-clear-methods-in-java-with-examples/)

**[Java . nio . short buffer](https://www.geeksforgeeks.org/tag/java-shortbuffer/)**类的 **clear()** 方法用来清除这个缓冲区。清除该缓冲区时，会进行以下更改:

*   The current position is set to zero.
*   The limit of this short buffer instance is set to capacity.
*   The tag of this short buffer instance, if any, will be discarded.

**语法:**

```java
public final ShortBuffer clear()
```

**返回值:**该方法在清除所有数据后返回这个**短缓冲区**实例。

以下是说明 clear()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            short[] darr = { 2, 3, 4, 6 };

            // creating object of ShortBuffer
            // and allocating size capacity
            ShortBuffer db
                = ShortBuffer.wrap(darr);

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

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            db.clear();

            // display position
            System.out.println("position after reset: "
                               + db.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("new position is less than "
                               + "the position we "
                               + "marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```java
position before reset: 4
position after reset: 0

```

**示例 2:**

```java
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        short[] carr = { 2, 10, 13, 23 };

        // creating object of ShortBuffer
        // and allocating size capacity
        ShortBuffer db = ShortBuffer.wrap(carr);

        // try to set the position at index 3
        db.position(3);

        // display position
        System.out.println("position before clear: "
                           + db.position());

        // try to call clear() to restore
        // to the position at index 0
        // by discarding the mark
        db.clear();

        // display position
        System.out.println("position after clear: "
                           + db.position());
    }
}
```

**输出:**

```java
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#clear--)
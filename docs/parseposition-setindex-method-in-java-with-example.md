# Java 中的 ParsePosition setIndex()方法，示例

> 原文:[https://www . geesforgeks . org/parse position-set index-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-setindex-method-in-java-with-example/)

**java.text.ParsePosition** 类的 **setIndex()** 方法用于设置这个 ParsePosition 对象的当前解析位置。

**语法:**

```java
public void setIndex(int index)
```

**参数**:该方法取当前解析位置将要设置的**整数索引**。

**返回值:**这个方法没有什么可返回的。

以下是说明**设置索引()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// setIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos
                = new ParsePosition(1);

            // set index for current
            // Parse Position object
            // using setIndex() method
            pos.setIndex(3);

            // getting the current
            // ParsePosition of
            int i = pos.getIndex();

            // display result
            System.out.println(
                "current parse position: "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```java
current parse position: 3

```

**例 2:**

```java
// Java program to demonstrate
// setIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos
                = new ParsePosition(500);

            // set index for current
            // Parse Position object
            // using setIndex() method
            pos.setIndex(30);

            // getting the current
            // ParsePosition of
            int i = pos.getIndex();

            // display result
            System.out.println(
                "current parse position: "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```java
current parse position: 30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # setIndex-int-](https://docs.oracle.com/javase/9/docs/api/java/text/ParsePosition.html#setIndex-int-)
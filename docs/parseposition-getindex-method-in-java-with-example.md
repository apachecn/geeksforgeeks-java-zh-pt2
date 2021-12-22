# 解析 Java 中的 getIndex()方法，示例

> 原文:[https://www . geesforgeks . org/parse position-getindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-getindex-method-in-java-with-example/)

**java.text.ParsePosition** 类的 **getIndex()** 方法用于检索这个 ParsePosition 对象的当前解析位置。

**语法:**

```java
public int getIndex()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回该解析位置对象的**当前解析位置**。

以下是说明 **getIndex()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getIndex() method

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

            // set index for the parsing error
            pos.setErrorIndex(3);

            // getting the current
            // ParsePosition of
            // using getIndex() method
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
current parse position: 1

```

**例 2:**

```java
// Java program to demonstrate
// getIndex() method

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
            // Parse Position
            pos.setIndex(3);

            // getting the current
            // ParsePosition of
            // using getIndex() method
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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # getIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/ParsePosition.html#getIndex--)
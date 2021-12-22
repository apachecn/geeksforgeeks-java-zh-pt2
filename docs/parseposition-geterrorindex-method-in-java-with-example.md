# Java 中的 ParsePosition getErrorIndex()方法，示例

> 原文:[https://www . geesforgeks . org/parse position-geterrindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-geterrorindex-method-in-java-with-example/)

**java.text.ParsePosition** 类的 **getErrorIndex()** 方法用于检索可能出现解析错误的索引。

**语法:**

```java
public int getErrorIndex()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回可能出现解析错误的索引。

以下是说明 **getErrorIndex()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getErrorIndex() method

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
                = new ParsePosition(0);

            // set index for the parsing error
            pos.setErrorIndex(3);

            // getting index at which
            // parsing error may come
            // using getErrorIndex() method
            int i = pos.getErrorIndex();

            // display result
            System.out.println(
                "index at which parse error may occur: "
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
index at which parse error may occur: 3

```

**例 2:**

```java
// Java program to demonstrate
// getErrorIndex() method

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
                = new ParsePosition(0);

            // getting index at which
            // parsing error may come
            // using getErrorIndex() method
            int i = pos.getErrorIndex();

            // display result
            if (i != -1)
                System.out.println(
                    "index at which parse error may occur: "
                    + Integer.toString(i));
            else
                System.out.println("error index is not set");
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```java
error index is not set

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # getErrorIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/ParsePosition.html#getErrorIndex--)
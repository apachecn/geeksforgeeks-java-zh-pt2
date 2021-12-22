# Java 中的 ParsePosition setErrorIndex()方法，示例

> 原文:[https://www . geeksforgeeks . org/parse position-seterrorindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-seterrorindex-method-in-java-with-example/)

**java.text.ParsePosition** 类的 **setErrorIndex()** 方法用于设置可能发生解析错误的索引。

**语法:**

```java
public void setErrorIndex(int ei)
```

**参数**:该方法将**整数 ei** 作为可能出现解析错误的参数。

**返回值:**这个方法没有什么可返回的。

以下是说明**设置错误索引()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// setErrorIndex() method

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
            // using setErrorIndex() method
            pos.setErrorIndex(3);

            // getting the current
            // ParsePosition of
            int i = pos.getErrorIndex();

            // display result
            System.out.println(
                "index at which error occurred: "
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
index at which error occurred: 3

```

**例 2:**

```java
// Java program to demonstrate
// setErrorIndex() method

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

            // set index for the parsing error
            // using setErrorIndex() method
            pos.setErrorIndex(3000);

            // getting the current
            // ParsePosition of
            int i = pos.getErrorIndex();

            // display result
            System.out.println(
                "index at which error occurred: "
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
index at which error occurred: 3000

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # setErrorIndex-int-](https://docs.oracle.com/javase/9/docs/api/java/text/ParsePosition.html#setErrorIndex-int-)
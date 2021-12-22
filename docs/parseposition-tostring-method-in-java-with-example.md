# Java 中的 ParsePosition toString()方法，示例

> 原文:[https://www . geesforgeks . org/parse position-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-tostring-method-in-java-with-example/)

**java.text.ParsePosition** 类的 **toString()** 方法用于检索以字符串形式表示的解析位置对象。
**语法:**

```
public String toString()
```

**参数**:该方法不接受任何参数作为参数。
**返回值:**这个方法返回以字符串形式表示的解析位置对象。
以下是举例说明 **toString()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

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

            // setting error index
            pos.setErrorIndex(30);

            // getting string representation
            // of this ParsePosition Object
            // using toString() method
            String i = pos.toString();

            // display result
            System.out.println(
                "ParsePosition: "
                + i);
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**Output:** 

```
ParsePosition: java.text.ParsePosition[index=500,errorIndex=30]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

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
                = new ParsePosition(-1);

            // setting error index
            pos.setErrorIndex(3000);

            // getting string representation
            // of this ParsePosition Object
            // using toString() method
            String i = pos.toString();

            // display result
            System.out.println(
                "ParsePosition: "
                + i);
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**Output:** 

```
ParsePosition: java.text.ParsePosition[index=-1,errorIndex=3000]
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # toString–T4】
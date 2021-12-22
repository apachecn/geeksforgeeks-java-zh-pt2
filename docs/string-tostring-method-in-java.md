# Java 中的字符串 toString()方法，示例

> 原文:[https://www . geesforgeks . org/string-tostring-method-in-Java/](https://www.geeksforgeeks.org/string-tostring-method-in-java/)

String toString()是 java.lang 的内置方法，它返回一个字符串。所以这里不执行实际转换。由于 toString()方法只是返回当前字符串，没有任何更改，因此不需要显式调用该字符串，通常是隐式调用。
**语法:**

```
public String toString()
```

**参数:**该方法不接受任何参数。
**返回值:**这个方法返回字符串本身。

**示例:**

```
Input: String("geeksforgeeks")
Output: geeksforgeeks

```

下面的程序说明了 Java.lang.String.toString()方法:
**程序 1:**

```
// Java program to illustrate the
// Java.lang.String.toString() method
import java.io.*;
public class Geeks {

    public static void main(String args[])
    {
        String Strobj = new String("Welcome to the world of geeks.");
        System.out.print("Output String Value :");
        System.out.println(Strobj.toString());

        String Strobj2 = new String("Let's make it simple for you.");
        System.out.print("Output String Value :");
        System.out.println(Strobj2.toString());
    }
}
```

**Output:**

```
Output String Value :Welcome to the world of geeks.
Output String Value :Let's make it simple for you.

```

**程序 2:**

```
// Java program to illustrate the
// Java.lang.String.toString() method
import java.io.*;
public class Geeks {

    public static void main(String args[])
    {
        String Strobj = new String("THank You");
        System.out.print("Output : ");
        System.out.println(Strobj.toString());
    }
}
```

**Output:**

```
Output : THank You

```
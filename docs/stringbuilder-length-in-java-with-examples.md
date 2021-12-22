# Java 中的 StringBuilder 长度()，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-length-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-length-in-java-with-examples/)

**字符串生成器类**的 **length()** 方法返回字符串生成器对象包含的字符数。此方法返回当前由该 StringBuilder 对象表示的字符序列的长度。

**语法:**

```
public int length()
```

**返回值:**该方法返回 StringBuilder 对象包含的字符序列的**长度。**

下面的程序演示了 StringBuilder 类的 length()方法:

**例 1:**

```
// Java program to demonstrate
// the length() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // get length of StringBuilder object
        int length = str.length();

        // print length
        System.out.println("length of String = "
                           + length);
    }
}
```

**Output:**

```
String = WelcomeGeeks
length of String = 12

```

**例 2:**

```
// Java program to demonstrate
// the length() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("India is Great");

        // print string
        System.out.println("String = "
                           + str.toString());

        // get length of StringBuilder object
        int length = str.length();

        // print length
        System.out.println("length of String = "
                           + length);
    }
}
```

**Output:**

```
String = India is Great
length of String = 14

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # length()](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#length())
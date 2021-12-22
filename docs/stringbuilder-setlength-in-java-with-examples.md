# Java 中的 StringBuilder setLength()，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-setlength-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-setlength-in-java-with-examples/)

[字符串生成器](https://www.geeksforgeeks.org/string-vs-stringbuilder-vs-stringbuffer-in-java/)的**设置长度(int newLength)** 方法用于**将字符序列的长度设置为等于 newLength** 。对于大于 0 且小于新长度的每个索引 k。如果作为参数传递的新长度小于旧长度，旧长度将更改为新长度。如果作为参数传递的新长度大于或等于旧长度，则在旧序列的末尾追加空字符(' \u0000 ')，这样长度就成为新长度参数。

**语法:**

```java
public void setLength(int newLength)
```

**参数:**
该方法接受一个参数**新长度**，该参数为整型值，指的是要设置的新序列长度。
**返回:**
此方法不返回任何内容。
**异常:**
如果新长度为负，则**indexout of boundsexception**。

下面的程序说明了 Java . lang . stringbuilder . setlength()方法:
**示例 1:**

```java
// Java program to demonstrate
// the setLength() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String length = "
                           + str.length() + 
                  " and contains = " + str);

        // set length equal to 10
        str.setLength(10);

        // print string
        System.out.println("After setLength() String = "
                           + str.toString());
    }
}
```

**输出:**

```java
String length = 12 and contains = WelcomeGeeks
After setLength() String = WelcomeGee

```

**例 2:**

```java
// Java program to demonstrate
// the setLength() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Tony Stark will die");

        // print string
        System.out.println("String length = "
                           + str.length() + 
           " and contains = \"" + str + "\"");

        // set length equal to 25
        str.setLength(25);

        // print string
        System.out.println("After setLength() String = \""
                           + str.toString() + "\"");
    }
}
```

**输出:**

```java
String length = 19 and contains = "Tony Stark will die"
After setLength() String = "Tony Stark will die      "

```

**示例 3:** 当传递负的新长度时:

```java
// Java program to demonstrate
// Exception thrown by the setLength() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Tony Stark");

        try {
            // pass length -15
            str.setLength(-15);
        }
        catch (Exception e) {

            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
java.lang.StringIndexOutOfBoundsException: String index out of range: -15
    at java.lang.AbstractStringBuilder.setLength(AbstractStringBuilder.java:207)
    at java.lang.StringBuilder.setLength(StringBuilder.java:76)
    at GFG.main(File.java:15)

```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # setLength(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#setLength(int))
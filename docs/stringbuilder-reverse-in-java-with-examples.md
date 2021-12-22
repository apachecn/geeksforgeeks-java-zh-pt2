# Java 中的 StringBuilder reverse()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-reverse-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-reverse-in-java-with-examples/)

StringBuilder 的**反转()**方法用于**反转 StringBuilder** 中的字符。该方法有助于将该字符序列替换为相反的序列。

**语法:**

```java
public java.lang.AbstractStringBuilder reverse()
```

**返回:**
该方法在反转字符后返回 StringBuilder 对象。

下面的程序说明了 Java . lang . stringbuilder . replace()方法:
**示例 1:**

```java
// Java program to demonstrate
// the reverse() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // reverse the string
        StringBuilder reverseStr = str.reverse();

        // print string
        System.out.println("Reverse String = "
                           + reverseStr.toString());
    }
}
```

**输出:**

```java
String = WelcomeGeeks
Reverse String = skeeGemocleW

```

**例 2:**

```java
// Java program to demonstrate
// the reverse() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("AAAABBBCCCC");

        // print string
        System.out.println("String = "
                           + str.toString());

        // reverse the string
        StringBuilder reverseStr = str.reverse();

        // print string
        System.out.println("Reverse String = "
                           + reverseStr.toString());
    }
}
```

**输出:**

```java
String = AAAABBBCCCC
Reverse String = CCCCBBBAAAA

```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # reverse()](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#reverse())
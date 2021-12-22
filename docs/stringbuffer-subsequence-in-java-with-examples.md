# Java 中的 StringBuffer 子序列()，示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-subsequence-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-subsequence-in-java-with-examples/)

StringBuffer 类的**子序列(int start，int end)** 方法是用于**返回位于该序列的索引开始和结束-1 之间的字符子序列**的内置方法。子序列以索引开始处的字符值开始，以(end-1)处的字符值结束。返回的子序列的长度是 end-start。所以如果开始等于结束，那么返回一个空的子序列。
**语法:**

```java
public CharSequence subSequence?(int start, int end)
```

**参数:**
该方法接受两个参数:

1.  **start** 是整型值，指子序列的开始 endex。
2.  **end** 为整型值，指子序列的最后一个 endex。

**返回:**
该方法返回范围从开始到结束-1 的指定子序列。
**异常:**
如果开始或结束都是负数，如果结束大于长度()，或者如果开始大于结束，则抛出**indexout of boundsexception**。
下面的程序说明了 Java . lang . stringbuffer . subsequel()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the subSequence() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("WelcomeGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get subSequence between index 0 to 7
        // using subSequence() and print
        System.out.println("SubSequence = "
                           + str.subSequence(0, 7));
    }
}
```

**输出:**

```java
String length = 12 and contains = WelcomeGeeks
SubSequence = Welcome
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the subSequence() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Indian Team Played Well");

        // print string
        System.out.println("String contains = " + str);

        // get subSequence between index 0 to 7
        // using subSequence() and print
        System.out.println("SubSequence = "
                           + str.subSequence(7, 18));
    }
}
```

**输出:**

```java
String contains = Indian Team Played Well
SubSequence = Team Played
```

**例 3:** 何时开始>何时结束:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Exception thrown by the subSequence() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Indian Team Played Well");

        try {
            // get subSequence between index 0 to 7
            // using subSequence() and print
            System.out.println(str.subSequence(19, 18));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
java.lang.StringIndexOutOfBoundsException: String index out of range: -1
    at java.lang.AbstractStringBuffer.substring(AbstractStringBuffer.java:935)
    at java.lang.StringBuffer.substring(StringBuffer.java:76)
    at java.lang.AbstractStringBuffer.subSequence(AbstractStringBuffer.java:912)
    at java.lang.StringBuffer.subSequence(StringBuffer.java:76)
    at GFG.main(File.java:16)
```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuffer . html # subsequel(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#subSequence(int, int))
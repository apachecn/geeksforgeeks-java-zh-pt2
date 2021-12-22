# Java 中 StringBuffer codePointBefore()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-codepoint before-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-codepointbefore-method-in-java-with-examples/)

**StringBuffer 类**的 **codePointBefore()** 方法是一种以索引为参数的方法，返回出现在该索引之前的字符的“Unicode 数字”。索引的值必须介于 0 到长度-1 之间。

如果(index–1)处的 char 值在低代理范围内，而(index–2)处的 char 值在高代理范围内，则方法返回代理对的补充代码点值。如果索引–1 处的字符值是不成对的低代理项或高代理项，则返回代理项值。

**语法:**

```java
public int codePointBefore(int index)
```

**参数:**该方法取一个参数**索引**，该索引是字符后面的字符的索引，该字符的 unicode 值将被返回。

**返回值:**该方法返回给定索引前字符的 **unicode 编号**。

**异常:**当索引为负或大于等于长度()时，此方法抛出**indexout of boundsexception**。

下面的程序说明了 codePointBefore()方法:

**例 1:**

```java
// Java program to demonstrate
// the codePointBefore() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("GeeksForGeeks Contribute");

        // get unicode of char at index 13
        // using codePointBefore() method
        int unicode = str.codePointBefore(14);

        // print char and Unicode
        System.out.println("Unicode of character"
                           + " at position 13 = "
                           + unicode);
    }
}
```

**Output:**

```java
Unicode of character at position 13 = 32

```

**示例 2:** 演示 IndexOutOfBoundsException

```java
// Java program to demonstrate
// exception thrown by codePointBefore() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("GEEKSFORGEEKS");

        try {

            // get unicode of char at position 22
            int unicode = str.codePointBefore(22);
        }

        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.StringIndexOutOfBoundsException:
 String index out of range: 22

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # code point before(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#codePointBefore(int))
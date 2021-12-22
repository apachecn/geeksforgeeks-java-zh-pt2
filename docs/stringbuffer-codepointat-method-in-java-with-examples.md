# Java 中 StringBuffer codePointAt()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-codepointat-in-Java-method-with-examples/](https://www.geeksforgeeks.org/stringbuffer-codepointat-method-in-java-with-examples/)

**StringBuffer 类**的 **codePointAt()** 方法返回 StringBuffer 包含的序列中该索引处的字符 Unicode 点。此方法返回该索引处的字符的“Unicodenumber”。索引的值必须介于 0 到长度-1 之间。
如果给定索引处的字符值位于高代理范围内，下一个索引小于该序列的长度，下一个索引处的字符值位于低代理范围内，则返回对应于该代理对的补充代码点。否则，返回给定索引处的字符值。

**语法:**

```java
public int codePointAt(int index)
```

**参数:**该方法取一个参数**索引**，该参数是代表要返回 unicode 值的字符的索引的 int 值。

**返回值:**该方法返回指定索引处字符的 **unicode 编号**。

**异常:**当索引为负或大于等于长度()时，此方法抛出**indexout of boundsexception**。

下面的程序演示了 StringBuffer 类的 codePointAt()方法:

**例 1:**

```java
// Java program to demonstrate
// the codePointAt() method

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        StringBuffer str = new StringBuffer();

        // add the String to StringBuffer Object
        str.append("Geeksforgeeks");

        // get unicode of char at position 10
        int unicode = str.codePointAt(10);

        // print the result
        System.out.println("Unicode of Character "
                           + "at Position 10 "
                           + "in StringBuffer = "
                           + unicode);
    }
}
```

**Output:**

```java
Unicode of Character at Position 10 in StringBuffer = 101

```

**示例 2:** 演示 IndexOutOfBoundsException

```java
// Java program demonstrate
// IndexOutOfBoundsException thrown by
// the codePointAt() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("GeeksForGeeks Contribute");

        try {

            // get char at position 25 which is
            // greater then length
            int i = str.codePointAt(25);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.StringIndexOutOfBoundsException: String index out of range: 25

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # code point(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#codePointAt(int))
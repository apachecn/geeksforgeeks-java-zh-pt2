# Java 中的 StringBuilder codePointBefore()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-code points-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-codepointbefore-in-java-with-examples/)

**StringBuilder 类**的 **codePointBefore()** 方法以索引为参数，返回 StringBuilder 包含的字符串中指定索引前的字符的“Unicode 编号”。索引引用字符值(Unicode 代码单位)，索引的值必须介于 0 到长度-1 之间。

如果(index–1)处的 char 值在低代理范围内，而(index–2)处的 char 值在高代理范围内，则方法返回代理对的补充代码点值。如果索引–1 处的字符值是不成对的低代理项或高代理项，则返回代理项值。

**语法:**

```
public int codePointBefore(int index)
```

**参数:**该方法接受一个 int 类型参数**索引**表示要返回 unicode 值的字符后面的字符的索引。

**返回值:**该方法返回给定索引前字符的**“unicode 数字”**。

**异常:**当索引为负或大于等于长度()时，此方法抛出**indexout of boundsexception**。

下面的程序演示了 StringBuilder 类的 codePointBefore()方法:

**例 1:**

```
// Java program to demonstrate
// the codePointBefore() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String is "
                           + str.toString());

        // get unicode of char at index 1
        // using codePointBefore() method
        int unicode = str.codePointBefore(2);

        // print char and Unicode
        System.out.println("Unicode of character"
                           + " at position 1 = " + unicode);

        // get unicode of char at index 10
        // using codePointBefore() method
        unicode = str.codePointBefore(11);

        // print char and Unicode
        System.out.println("Unicode of character"
                           + " at position 10 = "
                           + unicode);
    }
}
```

**Output:**

```
String is WelcomeGeeks
Unicode of character at position 1 = 101
Unicode of character at position 10 = 107

```

**示例 2:** 演示 IndexOutOfBoundsException

```
// Java program to demonstrate
// exception thrown by codePointBefore() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        try {

            // get unicode of char at position 1ength + 2
            int unicode = str.codePointBefore(
                str.length() + 2);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.StringIndexOutOfBoundsException:
 String index out of range: 14

```

**参考:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # code point before(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#codePointBefore(int))
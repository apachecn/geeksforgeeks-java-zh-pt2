# Java 中的 StringBuilder codePointAt()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-codepointat-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-codepointat-in-java-with-examples/)

**StringBuilder 类**的 **codePointAt(int index)** 方法以一个索引为参数，在 StringBuilder 包含的 String 中返回该索引处的一个字符 unicode 点，或者我们可以说 charPointAt()方法返回该索引处字符的“unicode 编号”。索引引用字符值(Unicode 代码单位)，索引的值必须介于 0 到长度-1 之间。

如果给定索引处的字符值位于高代理范围内，下一个索引小于该序列的长度，下一个索引处的字符值位于低代理范围内，则返回对应于该代理对的补充代码点。否则，返回给定索引处的字符值。

**语法:**

```
public int codePointAt(int index)
```

**参数:**该方法接受一个 int 类型参数**索引**，该索引代表要返回 unicode 值的字符的索引。

**返回值:**该方法返回指定位置字符的**“unicode 数字”**。

**异常:**当索引为负或大于等于长度()时，此方法抛出**indexout of boundsexception**。

以下程序演示了 StringBuilder 类的 codePointAt()方法:

例 1:

```
// Java program to demonstrate
// the codePointAt() method

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

        // add the String to StringBuilder Object
        str.append("Geek");

        // get unicode of char at position 1
        int unicode = str.codePointAt(1);

        // print the result
        System.out.println("StringBuilder Object"
                           + " contains = " + str);
        System.out.println("Unicode of Character"
                           + " at Position 1 "
                           + "in StringBuilder = "
                           + unicode);

        // get unicode of char at position 3
        unicode = str.codePointAt(3);

        // print the result
        System.out.println("Unicode of Character "
                           + "at Position 3 "
                           + "in StringBuilder = "
                           + unicode);
    }
}
```

**Output:**

```
StringBuilder Object contains = Geek
Unicode of Character at Position 1 in StringBuilder = 101
Unicode of Character at Position 3 in StringBuilder = 107

```

**例 2:**

```
// Java program to demonstrate
// the codePointAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String is " + str.toString());

        // loop through string and print every Character
        for (int i = 0; i < str.length(); i++) {

            // get char at position i
            char ch = str.charAt(i);

            // get unicode of char at position i
            int unicode = str.codePointAt(i);

            // print char and Unicode
            System.out.println("Unicode of Char " + ch
                               + " at position " + i
                               + " is " + unicode);
        }
    }
}
```

**Output:**

```
String is WelcomeGeeks
Unicode of Char W at position 0 is 87
Unicode of Char e at position 1 is 101
Unicode of Char l at position 2 is 108
Unicode of Char c at position 3 is 99
Unicode of Char o at position 4 is 111
Unicode of Char m at position 5 is 109
Unicode of Char e at position 6 is 101
Unicode of Char G at position 7 is 71
Unicode of Char e at position 8 is 101
Unicode of Char e at position 9 is 101
Unicode of Char k at position 10 is 107
Unicode of Char s at position 11 is 115

```

**示例 3:** 演示 IndexOutOfBoundsException

```
// Java program demonstrate
// IndexOutOfBoundsException thrown by
// the codePointAt() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        try {

            // get char at position out of range of index
            int i = str.codePointAt(str.length());
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.StringIndexOutOfBoundsException: 
String index out of range: 12

```

**参考:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # code point(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#codePointAt(int))
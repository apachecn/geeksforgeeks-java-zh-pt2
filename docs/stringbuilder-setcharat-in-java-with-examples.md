# Java 中的 StringBuilder setCharAt()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-setcharat-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-setcharat-in-java-with-examples/)

StringBuilder 类的 **setCharAt(int index，char ch)** 方法用于在作为 ch 传递的位置索引处设置字符。该方法将旧序列改变为代表与旧序列相同的新序列，唯一不同的是新字符 ch 出现在位置索引处。索引参数必须大于或等于 0，并且小于 StringBUilder 对象包含的字符串的长度。
**语法:**

```java
public void setCharAt(int index, char ch)
```

**参数:**
该方法接受两个参数:

1.  **索引**–整数类型值，指您要设置的字符索引。
2.  **ch**–引用新字符的字符类型值。

**返回:**
此方法不返回任何内容。
**异常:**
如果指数为负，大于 length()，则 IndexOutOfBoundsException。

下面的程序说明了 Java . lang . stringbuilder . setcharat()方法:
**示例 1:**

```java
// Java program to demonstrate
// the setCharAt() Method.

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

        // set char at index 2 to 'L'
        str.setCharAt(2, 'L');

        // print string
        System.out.println("After setCharAt() String = "
                           + str.toString());
    }
}
```

**输出:**

```java
String = WelcomeGeeks
After setCharAt() String = WeLcomeGeeks

```

**例 2:**

```java
// Java program to demonstrate
// the setCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Tony Stark will die");

        // print string
        System.out.println("String = "
                           + str.toString());

        // set char at index 9 to '1'
        str.setCharAt(9, '1');

        // print string
        System.out.println("After setCharAt() String = "
                           + str.toString());
    }
}
```

**输出:**

```java
String = Tony Stark will die
After setCharAt() String = Tony Star1 will die

```

**例 3:** 通过负指数时:

```java
// Java program to demonstrate
// Exception thrown by the setCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Tony Stark");

        try {
            // pass  index -15
            str.setCharAt(-15, 'A');
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
    at java.lang.AbstractStringBuilder.setCharAt(AbstractStringBuilder.java:407)
    at java.lang.StringBuilder.setCharAt(StringBuilder.java:76)
    at GFG.main(File.java:16)

```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # setCharAt(int，char)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#setCharAt(int, char))
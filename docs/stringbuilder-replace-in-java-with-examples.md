# StringBuilder 用示例替换 Java 中的()

> 原文:[https://www . geeksforgeeks . org/stringbuilder-replace-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-replace-in-java-with-examples/)

StringBuilder 类的 **replace(int start，int end，String str)** 方法用于将该序列的子串中的字符替换为指定 String 中的字符。子字符串从指定的索引开始处开始，并扩展到索引结束处的字符–1，如果不存在这样的字符，则扩展到序列的结尾。首先，删除子字符串的字符，并插入作为参数传递的字符串来代替这些字符。
**语法:**

```java
public StringBuilder replace?(int start, int end, String str)
```

**参数:**
该方法接受三个参数:

1.  **开始**–整数类型值，指开始索引。
2.  **end**–指结束索引的整型值。
3.  **字符串**–字符串类型值，指将替换先前内容的字符串。

**返回:**
这个方法在成功替换字符后返回 StringBuilder 对象。
**异常:**
如果起点为负，大于长度()，或大于终点，则为 StringIndexOutOfBoundsException。

下面的程序说明了 Java . lang . stringbuilder . replace()方法:
**示例 1:**

```java
// Java program to demonstrate
// the replace() Method.

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

        // replace Character from index 1 to 7 by "e are "
        StringBuilder strReturn = str.replace(1, 7, "e are ");

        // print string
        System.out.println("After Replace() String = "
                           + strReturn.toString());
    }
}
```

**输出:**

```java
String = WelcomeGeeks
After Replace() String = We are Geeks

```

**例 2:**

```java
// Java program to demonstrate
// the replace() Method.

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

        // replace Character from index 15 to 16 by " not "
        StringBuilder strReturn = str.replace(15, 16, " not ");

        // print string
        System.out.println("After Replace() String = "
                           + strReturn.toString());
    }
}
```

**输出:**

```java
String = Tony Stark will die
After Replace() String = Tony Stark will not die

```

**例 3:** 通过负指数时:

```java
// Java program to demonstrate
// Exception thrown by the replace() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Tony Stark");

        try {
            // replace Character from index -15 to 16 by "Captain America"
            StringBuilder strReturn = str.replace(-15, 16, "Captain America");
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
    at java.lang.AbstractStringBuilder.replace(AbstractStringBuilder.java:851)
    at java.lang.StringBuilder.replace(StringBuilder.java:262)
    at GFG.main(File.java:17)

```

**示例 4:** 当传递的开始索引大于结束索引时:

```java
// Java program to demonstrate
// Exception thrown by the replace() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Tony Stark");

        try {
            // replace Character from index 5 to 3 by "Captain America"
            StringBuilder strReturn = str.replace(5, 3, "Captain America");
        }
        catch (Exception e) {

            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
java.lang.StringIndexOutOfBoundsException: start > end
    at java.lang.AbstractStringBuilder.replace(AbstractStringBuilder.java:855)
    at java.lang.StringBuilder.replace(StringBuilder.java:262)
    at GFG.main(File.java:17)

```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # replace(int，int，java.lang.String)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#replace(int, int, java.lang.String))
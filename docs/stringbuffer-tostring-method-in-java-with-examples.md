# Java 中 StringBuffer toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-tostring-method-in-java-with-examples/)

**StringBuffer 类**的 **toString()** 方法是用于返回表示 StringBuffer 对象包含的数据的字符串的内置方法。创建并初始化一个新的 String 对象，从这个 StringBuffer 对象中获取字符序列，然后由 toString()返回 String。对象包含的对该序列的后续更改不会影响字符串的内容。

**语法:**

```java
public abstract String toString()
```

**返回值:**该方法返回表示 StringBuffer 对象包含的数据的**字符串**。****

下面的程序说明了 StringBuffer.toString()方法:

**例 1:**

```java
// Java program to demonstrate
// the toString() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("GeeksForGeeks");

        // print string
        System.out.println("String contains = "
                           + str.toString());
    }
}
```

**Output:**

```java
String contains = GeeksForGeeks

```

**例 2:**

```java
// Java program to demonstrate
// the toString() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer(
                "Geeks for Geeks contribute");

        // print string
        System.out.println("String contains = "
                           + str.toString());
    }
}
```

**Output:**

```java
String contains = Geeks for Geeks contribute

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuffer . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#toString())
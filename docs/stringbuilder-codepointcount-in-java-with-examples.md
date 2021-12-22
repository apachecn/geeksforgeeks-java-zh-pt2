# Java 中的 StringBuilder codePointCount()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-codepointcount-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-codepointcount-in-java-with-examples/)

**StringBuilder 类**的 **codePointBefore()** 方法返回 StringBuilder 包含的字符串中指定文本范围内的 Unicode 码点数。此方法将两个索引作为参数-第一个 beginIndex 表示文本范围第一个字符的索引，第二个 endIndex 表示文本范围最后一个字符之后的索引。索引引用字符值(Unicode 代码单位)，索引的值必须介于 0 到长度-1 之间。文本范围从 beginIndex 开始，延伸到索引 endIndex–1 处的字符。因此，文本范围的长度(以字符为单位)是 **endIndex-beginIndex** 。

**语法:**

```java
public int 
    codePointCount(int beginIndex, int endIndex)
```

**参数:**该方法接受两个参数

*   **beginIndex:** 文本范围第一个字符的索引。
*   **endIndex:** 文本范围最后一个字符后的索引。

**返回值:**该方法返回**指定文本范围内的 Unicode 码点数。**

**异常:**如果出现以下情况，此方法将抛出**指数超出边界异常**:

*   beginIndex 小于零，
*   或者 endIndex 大于字符串的长度，
*   或者 beginIndex 大于 endIndex。

以下程序演示了 StringBuilder 类的 codePointCount()方法:

**例 1:**

```java
// Java program to demonstrate
// the codePointCount() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String = " + str.toString());

        // returns the codepoint count from index 2 to 8
        int codepoints = str.codePointCount(2, 8);
        System.out.println("No of Unicode code points = "
                           + codepoints);
    }
}
```

**Output:**

```java
String = WelcomeGeeks
No of Unicode code points = 6

```

**例 2:**

```java
// Java program to demonstrate
// the codePointCount() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("GeeksForGeeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // returns the codepoint count
        // from index 3 to 7
        int
            codepoints
            = str.codePointCount(3, 7);
        System.out.println("No of Unicode code points"
                           + " between index 3 and 7 = "
                           + codepoints);
    }
}
```

**Output:**

```java
String = GeeksForGeeks
No of Unicode code points between index 3 and 7 = 4

```

**示例 3:** 演示 IndexOutOfBoundsException

```java
// Java program to demonstrate
// exception thrown by the codePointCount() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("GeeksForGeeks");

        try {

            // make beginIndex greater than endIndex
            int codepoints = str.codePointCount(7, 4);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.IndexOutOfBoundsException

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # codePointCount(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#codePointCount(int, int))
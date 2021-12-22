# Java 中的 StringBuffer codePointCount()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-codepointcount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-codepointcount-method-in-java-with-examples/)

**StringBuffer 类**的 **codePointCount()** 方法用于返回 StringBuffer 包含的字符串的指定范围 beginIndex 到 endIndex 内的 Unicode 码点数。此方法将 beginIndex 和 endIndex 作为参数，其中 beginIndex 是文本范围第一个字符的索引，endIndex 是文本范围最后一个字符之后的索引。索引引用字符值(Unicode 代码单位)，索引的值必须介于 0 到长度-1 之间。该范围从索引开始，到索引 endIndex–1 处的字符结束。因此，文本范围的长度(以字符为单位)是 endIndex-beginIndex。

**语法:**

```
public int codePointCount(int beginIndex,
                               int endIndex)
```

**参数:**该方法取两个参数:

*   **beginIndex** :表示文本范围第一个字符索引的 int 值。
*   **endIndex** :表示文本范围最后一个字符后的索引的 int 值。

**返回值:**该方法返回表示指定文本范围内 Unicode 码点数的**整数值**。

**异常:**如果出现以下情况，此方法将抛出**指数超出边界异常**:

*   beginIndex 小于零，
*   或者 endIndex 大于字符串的长度，
*   或者 beginIndex 大于 endIndex。

下面的程序说明了 StringBuffer.codePointCount()方法:

**例 1:**

```
// Java program to demonstrate
// the codePointCount() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("Welcome to GeeksforGeeks");

        // print string
        System.out.println("String = " + str.toString());

        // returns the codepoint count from index 4 to 10
        int codepoints = str.codePointCount(4, 10);

        System.out.println("No of Unicode code points "
                           + " between index 4 and index 10 = "
                           + +codepoints);
    }
}
```

**Output:**

```
String = Welcome to GeeksforGeeks
No of Unicode code points  between index 4 and index 10 = 6

```

**例 2:**

```
// Java program to demonstrate
// the codePointCount() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("GeeksForGeeks contribute");

        // print string
        System.out.println("String = "
                           + str.toString());

        // returns the codepoint count
        // from index 3 to 7
        int
            codepoints
            = str.codePointCount(13, 17);

        System.out.println("No of Unicode code points"
                           + " between index 13 and 17 = "
                           + codepoints);
    }
}
```

**Output:**

```
String = GeeksForGeeks contribute
No of Unicode code points between index 13 and 17 = 4

```

**示例 3:** 演示 IndexOutOfBoundsException

```
// Java program to demonstrate
// exception thrown by the codePointCount() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("GeeksForGeeks");

        try {

            // make beginIndex greater than endIndex
            int codepoints = str.codePointCount(2, 0);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.IndexOutOfBoundsException

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # code point count(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#codePointCount(int, int))
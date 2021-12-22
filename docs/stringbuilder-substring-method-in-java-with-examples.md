# Java 中 StringBuilder substring()方法，带示例

> 原文:[https://www . geesforgeks . org/stringbuilder-substring-in-Java-method-with-examples/](https://www.geeksforgeeks.org/stringbuilder-substring-method-in-java-with-examples/)

在 StringBuilder 类中，根据传递给它的参数，有两种类型的子字符串方法。

### 子字符串(int start)

**StringBuilder 类**的**子串(int start)** 方法是用于从索引开始返回子串并扩展到该序列结束的内置方法。此方法返回的字符串包含从索引开始到旧序列结束的所有字符。

**语法:**

```
public String substring(int start)
```

**参数:**该方法只接受一个参数 **start** ，为整型值，指子串的起始索引。

**返回值:**该方法返回位于旧序列开始到结束范围内的子串**。**

**异常:**如果 start 小于零，或者大于这个对象的长度，这个方法抛出**StringIndexOutOfBoundsException**。

下面的程序说明了 StringBuilder substring()方法:

**例 1:**

```
// Java program to demonstrate
// the substring() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("GeeksForGeeks");

        // print string
        System.out.println("String contains = "
                           + str);

        // get substring start from index 5
        // using substring() and print results
        System.out.println("SubSequence = "
                           + str.substring(5));
    }
}
```

**Output:**

```
String contains = GeeksForGeeks
SubSequence = ForGeeks

```

**示例 2:** 演示 StringIndexOutOfBoundsException

```
// Java program to demonstrate
// Exception thrown by the substring() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Indian Team Played Well");

        try {
            // get substring starts from index -7
            // using substring() and print
            str.substring(-7);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.StringIndexOutOfBoundsException: String index out of range: -7

```

### 子字符串(int 开始，int 结束)

**StringBuilder 类**的**子串(int start，int end)** 方法是用于从索引开始返回子串的内置方法，并扩展到该序列的索引 end-1。此方法返回的字符串包含旧序列从索引开始到索引结束-1 的所有字符。

**语法:**

```
public String substring(int start)
```

**参数:**这个方法接受两个参数**开始**是整型值指子串的开始索引，**结束**也是整型值指子串的结束索引。

**返回值:**该方法返回**子串**位于旧序列的范围索引开始到索引结束-1。

**异常:**如果开始或结束为负或大于长度()，或开始大于结束，此方法抛出**StringIndexOutOfBoundsException**。

下面的程序说明了 StringBuilder.substring()方法:

**例 1:**

```
// Java program to demonstrate
// the substring() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("GeeksForGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get substring start from index 5 to index 8
        // using substring() and print results
        System.out.println("SubSequence = "
                           + str.substring(5, 8));
    }
}
```

**Output:**

```
String contains = GeeksForGeeks
SubSequence = For

```

**示例 2:** 演示 StringIndexOutOfBoundsException

```
// Java program to demonstrate
// Exception thrown by the substring() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Indian Team Played Well");

        try {
            // get substring starts from index 7
            // and end at index 3
            // using substring() and print
            str.substring(9, 3);
        }

        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.StringIndexOutOfBoundsException: String index out of range: -6

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # substring(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#substring(int, int))
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # substring(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#substring(int))
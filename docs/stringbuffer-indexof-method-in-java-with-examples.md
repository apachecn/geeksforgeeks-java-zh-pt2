# Java 中 StringBuffer indexOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-indexof-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-indexof-method-in-java-with-examples/)

在 **StringBuffer 类**中，根据传递给它的参数，有两种类型的 indexOf()方法。

### 索引（字符串字符串）

**StringBuffer 类**的 **indexOf(String str)** 方法用于从该对象包含的序列中返回第一次出现作为参数的传递的子字符串的字符串索引。如果子字符串字符串不存在，则返回-1 代替索引。

**语法:**

```
public int indexOf(String str)
```

**参数:**这个方法接受**字符串**，它是子串类型值，指的是我们想要获取其索引的字符串。
**返回值:**该方法返回**传递的子串第一次出现的索引**，如果不存在这样的子串，则返回-1。

下面的程序说明了 StringBuffer.indexOf()方法:

**示例 1:** 当传递的子串出现在序列中时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("GeeksForGeeks");

        // print string
        System.out.println("String: " + str);

        // get index of string For
        int index = str.indexOf("For");

        // print results
        System.out.println("index of 'For': "
                           + index);
    }
}
```

**Output:**

```
String: GeeksForGeeks
index of 'For': 5

```

**示例 2:** 当传递的子串在序列中不存在时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Geeks for Geeks contribute");

        // print string
        System.out.println("String: " + str);

        // get index of string article
        int index = str.indexOf("article");

        // print results
        System.out.println("index of 'article': "
                           + index);
    }
}
```

**Output:**

```
String: Geeks for Geeks contribute
index of 'article': -1

```

### indexOf（String str， int fromIndex）：

**StringBuffer 类**的 **indexOf(String str，int fromIndex)** 方法用于从指定的索引“fromIndex”开始，返回字符串中第一个出现的传递子字符串的索引。如果子字符串字符串不存在，则返回-1。fromIndex 是整型值，指搜索开始的索引。如果字符串出现在搜索开始的索引之前，但不在之后，则将返回-1。

**语法:**

```
public int indexOf(String str, int fromIndex)
```

**参数:**这个方法接受两个一参数 **str** 是 String 类型的值指的是我们想要获取其索引的 String，而 **fromIndex** 是 Integer 类型的值指的是开始搜索的索引。

**返回:**这个方法返回**从指定的索引开始的传递的子串的第一次出现的索引**，如果不存在这样的子串，则返回-1。

下面的程序说明了 StringBuffer.indexOf()方法:

**示例 1:** 当传递的子串出现在序列中时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("GeeksForGeeks");

        // print string
        System.out.println("String: " + str);

        // get index of string Form index 3
        int index = str.indexOf("For", 3);

        // print results
        System.out.println("index of 'For': "
                           + index);
    }
}
```

**Output:**

```
String: GeeksForGeeks
index of 'For': 5

```

**示例 2:** 当传递的子串出现在序列中，但搜索索引大于子串索引时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {

    public static void main(String[] args)
    {
        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Geeks for Geeks contribute");

        // print string
        System.out.println("String: " + str);

        // get index of string Geeks from index 15
        int index = str.indexOf("Geeks", 15);

        // print results
        System.out.println("index of 'Geeks ': "
                           + index);
    }
}
```

**Output:**

```
String: Geeks for Geeks contribute
index of 'Geeks ': -1

```

[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # index of(Java . lang . string，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#indexOf(java.lang.String, int))
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # index of(Java . lang . string)】](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#indexOf(java.lang.String))
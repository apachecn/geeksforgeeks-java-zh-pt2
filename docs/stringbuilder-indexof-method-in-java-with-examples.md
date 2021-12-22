# Java 中 StringBuilder indexOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-indexof-method-in-java-with-examples/)

在 StringBuilder 类中，根据传递给它的参数，有两种类型的 indexOf()方法。

### 索引（字符串字符串）

**StringBuilder 类**的 **indexOf(String str)** 方法是一种内置方法，用于返回字符串中作为参数传递的子字符串首次出现的索引。如果子字符串字符串不存在，则返回-1。

**语法:**

```
public int indexOf(String str)
```

**参数:**该方法只接受一个参数**字符串**，该参数为字符串类型值，指的是需要索引的字符串。

**返回值:**这个方法返回**传递的子串第一次出现的索引**，如果不存在这样的子串，返回-1。

下面的程序说明了 StringBuilder.indexOf()方法:

**示例 1:** 当传递的子串出现在序列中时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("GeeksForGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get index of string For
        int index = str.indexOf("For");

        // print results
        System.out.println("index of string 'For' = "
                           + index);
    }
}
```

**Output:**

```
String contains = GeeksForGeeks
index of string 'For' = 5

```

**示例 2:** 当传递的子串在序列中不存在时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder(
                "Geeks for Geeks contribute");

        // print string
        System.out.println("String contains = "
                           + str);

        // get index of string article
        int index = str.indexOf("article");

        // print results
        System.out.println("Index of string"
                           + " 'article' = "
                           + index);
    }
}
```

**Output:**

```
String contains = Geeks for Geeks contribute
Index of string 'article' = -1

```

### indexOf（String str， int fromIndex）

**StringBuilder 类**的 **indexOf(String str，int fromIndex)** 方法是一种内置方法，用于从指定的索引“fromIndex”开始，返回字符串中第一次出现的作为参数的传递子字符串的索引。如果子字符串字符串不存在，则返回-1。 **fromIndex** 是整型值，是指开始搜索的索引。这个方法返回的索引是从序列的开始计算的，唯一的区别是搜索开始的索引是在这个方法中给出的。如果字符串出现在搜索开始的索引之前，但不在之后，则将返回-1。

**语法:**

```
public int indexOf(String str, int fromIndex)
```

**参数:**该方法接受两个参数:

*   **字符串:**是字符串类型值，是指需要索引的字符串。
*   **fromIndex:** 是整型值，指开始搜索的索引。

**返回值:**这个方法返回**从指定的索引开始的传递的子串的第一次出现的索引**，如果不存在这样的子串，则返回-1。

下面的程序说明了 StringBuilder.indexOf()方法:

**示例 1:** 当传递的子串出现在序列中时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("GeeksForGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get index of string Form index 3
        int index = str.indexOf("For", 3);

        // print results
        System.out.println("index of string"
                           + " \"For\" = "
                           + index);
    }
}
```

**Output:**

```
String contains = GeeksForGeeks
index of string "For" = 5

```

**示例 2:** 当传递的子串出现在序列中，但搜索索引大于子串索引时。

```
// Java program to demonstrate
// the indexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("Geeks for Geeks contribute");

        // print string
        System.out.println("String contains = " + str);

        // get index of string Geeks from index 15
        int index = str.indexOf("Geeks", 15);

        // print results
        System.out.println("index of string 'Geeks ' = "
                           + index);
    }
}
```

**Output:**

```
String contains = Geeks for Geeks contribute
index of string 'Geeks ' = -1

```

**参考文献:**

*   [https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # index of(Java . lang . string，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#indexOf(java.lang.String, int))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # indexOf(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#indexOf(java.lang.String))
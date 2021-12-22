# Java 中 StringBuffer lastIndexOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-last indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-lastindexof-method-in-java-with-examples/)

在 StringBuffer 类中，根据传递给它的参数，有两种类型的 lastIndexOf()方法。

### lastIndexOf（String str）

**StringBuffer 类**的 **lastIndexOf(字符串字符串)**方法是一种内置方法，用于返回字符串中作为参数传递的子字符串的最后一次出现的索引。空字符串“”的最后一次出现被认为出现在索引值 this.length()处。如果子字符串字符串不存在，则返回-1。

**语法:**

```java
public int lastIndexOf(String str)
```

**参数:**这个方法只接受一个参数 **str** ，它是 String 类型的值，指的是我们想要得到的最后一次出现的索引的字符串。

**返回值:**这个方法返回**传递的子串最后一次出现的索引**，如果不存在这样的子串，返回-1。

下面的程序说明了 Java . lang . stringbuffer . LastIndexof()方法:

**示例 1:** 当序列中存在传递的子串时。

```java
// Java program to demonstrate
// the lastIndexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("GeeksForGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get index of string For
        int index = str.lastIndexOf("Geeks");

        // print results
        System.out.println("Index of last occurrence"
                           + " string \"Geeks\"= "
                           + index);
    }
}
```

**Output:**

```java
String contains = GeeksForGeeks
Index of last occurrence string "Geeks"= 8

```

**示例 2:** 当传递的子串在序列中不存在时。

```java
// Java program to demonstrate
// the lastIndexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer(
                "Geeks for Geeks contribute");

        // print string
        System.out.println("String contains = " + str);

        // get index of string article
        int index = str.lastIndexOf("article");

        // print results
        System.out.println("Index of string"
                           + " 'article' = "
                           + index);
    }
}
```

**Output:**

```java
String contains = Geeks for Geeks contribute
Index of string 'article' = -1

```

### lastIndexOf（String str， int fromIndex）

**StringBuffer 类**的 **lastIndexOf(String str，int fromIndex)** 方法是一种内置方法，用于返回字符串中作为参数传递的子字符串首次出现的索引，从指定的索引“fromIndex”开始向后搜索。如果子字符串字符串不存在，则返回-1。 **fromIndex** 是整型值，指的是开始搜索的索引，但该搜索是从索引“fromIndex”向后进行的。这个方法返回的索引是从序列的开始计算的，唯一的区别是搜索开始的索引是在这个方法中给出的。如果字符串出现在搜索开始的索引之后，但不是之前，那么-1 将返回。

**语法:**

```java
public int lastIndexOf(String str, int fromIndex)
```

**参数:**该方法接受两个一参数:

*   **字符串**是字符串类型的值，指的是要获取其索引的字符串
*   **fromIndex** 是整型值，指的是开始向后搜索的索引。

**返回:**这个方法返回**从指定的索引开始的传递的子串最后一次出现的索引**，如果没有这样的子串，则返回-1。

下面的程序说明了 StringBuffer.lastIndexOf()方法:

**示例 1:** 当传递的子串出现在序列中时。

```java
// Java program to demonstrate
// the lastIndexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("GeeksForGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get index of string Form index 3
        int index = str.lastIndexOf("For", 8);

        // print results
        System.out.println("index of last occurrence"
                           + " string \"For\" = "
                           + index);
    }
}
```

**Output:**

```java
String contains = GeeksForGeeks
index of last occurrence string "For" = 5

```

**例 2:** 当 fromIndex 为<子串的最后一个出现索引时

```java
// Java program to demonstrate
// the lastIndexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Geeks for Geeks contribute");

        // print string
        System.out.println("String contains = " + str);

        // get index of string Geeks from index 15
        int index = str.lastIndexOf("contribute", 10);

        // print results
        System.out.println("index of string"
                           + " 'contribute ' = "
                           + index);
    }
}
```

**Output:**

```java
String contains = Geeks for Geeks contribute
index of string 'contribute ' = -1

```

**参考文献**:

*   [https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # lastindexof(Java . lang . string，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#lastIndexOf(java.lang.String, int))
*   [https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # lastindexof(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#lastIndexOf(java.lang.String))
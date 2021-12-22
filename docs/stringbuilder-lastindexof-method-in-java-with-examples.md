# Java 中 StringBuilder lastIndexOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-last indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-lastindexof-method-in-java-with-examples/)

在 StringBuilder 类中，根据传递给它的参数，有两种类型的 lastIndexOf()方法。

### lastIndexOf（String str）

**字符串生成器类**的 **lastIndexOf(字符串字符串)**方法是一种内置方法，用于返回字符串中作为参数传递的子字符串的最后一次出现的索引。空字符串“”的最后一次出现被认为出现在索引值 this.length()处。如果子字符串字符串不存在，则返回-1。

**语法:**

```
public int lastIndexOf(String str)
```

**参数:**这个方法只接受一个参数 **str** ，它是 String 类型的值，指的是我们想要得到的最后一次出现的索引的字符串。

**返回值:**这个方法返回**传递的子串最后一次出现的索引**，如果不存在这样的子串，返回-1。

下面的程序说明了 Java . lang . StringBuilder . LastIndexof()方法:

**示例 1:** 当序列中存在传递的子串时。

```
// Java program to demonstrate
// the lastIndexOf() Method.

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
        int index = str.lastIndexOf("Geeks");

        // print results
        System.out.println("Index of last occurrence"
                           + " string \"Geeks\"= "
                           + index);
    }
}
```

**Output:**

```
String contains = GeeksForGeeks
Index of last occurrence string "Geeks"= 8

```

**示例 2:** 当传递的子串在序列中不存在时。

```
// Java program to demonstrate
// the lastIndexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder(
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

```
String contains = Geeks for Geeks contribute
Index of string 'article' = -1

```

### lastIndexOf（String str， int fromIndex）

**字符串构建器类**的 **lastIndexOf(字符串，int fromIndex)** 方法是用于返回原始字符串中子字符串索引的内置方法。但是子串的搜索是从 0 索引开始到索引**从索引**开始。在这个新的范围(0-fromIndex)中，现在找到了子字符串的最后一个匹配项，并且这个函数返回了起始索引。如果在该范围内找不到子字符串，则返回-1。请注意，将搜索最后一个子字符串的范围的起点始终为零。用户只能设置终点。

**语法:**

```
public int lastIndexOf(String str, int fromIndex)
```

**参数:**该方法接受两个一参数:

*   **字符串**是字符串类型的值，指的是我们试图获取其索引的子字符串
*   **fromIndex** 是整型值，指的是开始向后搜索的索引。

**返回:**这个方法返回**从指定的索引开始的传递的子串最后一次出现的索引**，如果没有这样的子串，则返回-1。

下面的程序举例说明了 StringBuilder.lastIndexOf()方法:

**示例 1:** 当传递的子串出现在序列中时。

```
// Java program to demonstrate
// the lastIndexOf() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("WeGeeksLoveGeeksForGeeks");

        // print string
        System.out.println("String contains = " + str);

        // get index of last occurrence of substring till 15th position of original String
        int index = str.lastIndexOf("Geeks", 15);

        // print results
        System.out.println("index of last occurrence"
                           + " string \"Geeks\" = "
                           + index);
    }
}
```

**Output:**

```
String contains = WeGeeksLoveGeeksForGeeks
index of last occurrence string "Geeks" = 11

```

**例 2:** 当 fromIndex 为<子串的最后一个出现索引时

```
// Java program to demonstrate
// the lastIndexOf() Method.

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
        int index = str.lastIndexOf("contribute", 10);

        // print results
        System.out.println("index of string"
                           + " 'contribute ' = "
                           + index);
    }
}
```

**Output:**

```
String contains = Geeks for Geeks contribute
index of string 'contribute ' = -1

```

**参考文献**:

*   [https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # lastindexof(Java . lang . string，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#lastIndexOf(java.lang.String, int))
*   [https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # lastindexof(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#lastIndexOf(java.lang.String))
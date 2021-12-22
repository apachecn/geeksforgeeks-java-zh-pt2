# Java 中字符串和 StringBuffer 的排序集合

> 原文:[https://www . geesforgeks . org/sorting-collection-string-stringbuffer-Java/](https://www.geeksforgeeks.org/sorting-collection-string-stringbuffer-java/)

对对象集合进行排序有两种方式:

*   通过实现[可比](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)(自然顺序)，例如字符串按字母顺序排序。意思是 B 在 A 之前，10 在 2 之前。
*   通过实现[比较器(自定义顺序)](https://www.geeksforgeeks.org/comparator-interface-java/)，它可以是任何顺序。
*   使用 Collections 实用程序类的 [Collections.sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/) 方法。

[阅读更多关于可比和比较的信息](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)
对于分类收藏，我们可以使用以下收藏:

*   TreeSet(树集)
*   树图

如果是字符串，排序将自动按自然顺序进行。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to sort String objects using TreeSet
import java.util.Set;
import java.util.TreeSet;

public class Test {
    public static void main(String[] args)
    {
        Set<String> str = new TreeSet<String>();
        str.add("Sohan");
        str.add("Raja");
        str.add("Harish");
        str.add("Ram");
        System.out.println(str);
    }
}
```

**输出:**

```java
[Harish, Raja, Ram, Sohan]

```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that simple sorting
// StringBuffer objects does work.
import java.util.Set;
import java.util.TreeSet;

public class Test {

    public static void main(String[] args)
    {
        Set<StringBuffer> str = new TreeSet<>();
        str.add(new StringBuffer("Sohan"));
        str.add(new StringBuffer("Raja"));
        str.add(new StringBuffer("Harish"));
        str.add(new StringBuffer("Ram"));
        System.out.println(str);
    }
}
```

**Output**

```java
[Harish, Raja, Ram, Sohan]

```

字符串类实现可比接口，而字符串缓冲和字符串构建类不实现可比接口。请参见以下字符串、字符串缓冲区和字符串构建器类的签名:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public final class String
    extends Object
        implements Serializable,
    Comparable, CharSequence
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public final class StringBuffer
    extends Object
        implements Serializable,
    CharSequence
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public final class StringBuilder
    extends Object
        implements Serializable,
    CharSequence
```

对 StringBuffer、StringBuilder 类进行排序的方法有很多。下面给出了一些方法:

*   通过实现比较器接口
*   通过使用 StringBuffer.toString()方法将 StringBuffer 转换为 String

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate sorting
// of StringBuffer objects using Comparator
// interface.
import java.util.Comparator;
import java.util.Set;
import java.util.TreeSet;

public class Test implements Comparator<StringBuffer> {
    @Override public int compare(StringBuffer s1, StringBuffer s2)
    {
        return s1.toString().compareTo(s2.toString());
    }

    public static void main(String[] args)
    {
        Set<StringBuffer> str = new TreeSet<>(new Test());
        str.add(new StringBuffer("Sohan"));
        str.add(new StringBuffer("Raja"));
        str.add(new StringBuffer("Harish"));
        str.add(new StringBuffer("Ram"));
        System.out.println(str);
    }
}
```

**输出:**

```java
[Harish, Raja, Ram, Sohan]

```

本文由**赛义德·阿里·汗供稿，由**Soumyaranjan Panda 即兴创作。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# Java 中字符串 vs StringBuilder vs StringBuffer

> 原文:[https://www . geesforgeks . org/string-vs-stringbuilder-vs-stringbuffer-in-Java/](https://www.geeksforgeeks.org/string-vs-stringbuilder-vs-stringbuffer-in-java/)

字符串是一系列字符。在 java 中，String 的对象是不可变的，这意味着一个常量，一旦创建就不能更改。[初始化一个字符串](https://www.geeksforgeeks.org/how-to-initialize-and-compare-strings-in-java/)是一个重要的支柱，需要有更深的理解作为先决条件。现在，我们将证明让我们考虑下面的三个串联函数的代码，这三个串联函数具有三种不同类型的参数:String、StringBuffer 和 StringBuilder。让我们通过下面的一个 java 程序来阐明它们之间的理解，我们将从生成的输出中得出结论，以找出 Java 中 String 与 StringBuilder 和 StringBuffer 之间的区别。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate difference between
// String, StringBuilder and StringBuffer

// Main class
class GFG {

    // Method 1
    // Concatenates to String
    public static void concat1(String s1)
    {
        s1 = s1 + "forgeeks";
    }

    // Method 2
    // Concatenates to StringBuilder
    public static void concat2(StringBuilder s2)
    {
        s2.append("forgeeks");
    }

    // Method 3
    // Concatenates to StringBuffer
    public static void concat3(StringBuffer s3)
    {
        s3.append("forgeeks");
    }

    // Method 4
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        // String 1
        String s1 = "Geeks";

        // Calling above defined method
        concat1(s1);

        // s1 is not changed
        System.out.println("String: " + s1);

        // String 1
        StringBuilder s2 = new StringBuilder("Geeks");

        // Calling above defined method
        concat2(s2);

        // s2 is changed
        System.out.println("StringBuilder: " + s2);

        // String 3
        StringBuffer s3 = new StringBuffer("Geeks");

        // Calling above defined method
        concat3(s3);

        // s3 is changed
        System.out.println("StringBuffer: " + s3);
    }
}
```

**Output**

```java
String: Geeks
StringBuilder: Geeksforgeeks
StringBuffer: Geeksforgeeks
```

**输出解释:**

*   **Concat1** :在这个方法中，我们传递一个字符串“Geeks”，执行“S1 = S1+”forgeks。main()传递的字符串没有改变，这是因为 string 是**不可变的**。更改 string 的值会创建另一个对象，concat1()中的 s1 存储新字符串的引用。main()和 cocat1()中的引用 s1 引用不同的字符串。
*   **Concat2** :在这个方法中，我们传递一个字符串“Geeks”并执行“S2 . append(“forgeeks”)”，它将字符串的实际值(在 main 中)更改为“Geeksforgeeks”。这是因为 StringBuilder 是**可变的**这一简单事实，因此改变了它的值。
*   **Concat3** : StringBuilder 与 StringBuffer 类似，除了线程安全这个关键区别，其他地方都可以兼容。StringBuffer 是线程安全的，而 StringBuilder 不保证线程安全，这意味着 StringBuffer 中存在同步方法，一次控制一个线程的访问，而 StringBuilder 中看不到它，因此是线程不安全的。

> **注意:**极客们现在你们一定在想什么时候用哪一个，做如下参考:
> 
> *   如果字符串在整个程序中保持不变，那么使用字符串类对象，因为字符串对象是不可变的。
> *   如果字符串可以改变(例如:字符串构造中的大量逻辑和操作)，并且只能从一个线程访问，那么使用 StringBuilder 就足够了。
> *   如果一个字符串可以改变并且将被多个线程访问，那么使用一个 StringBuffer，因为 StringBuffer 是同步的，所以你有线程安全。
> *   如果你不想线程安全，你也可以使用 StringBuilder 类，因为它不是同步的。

**Java 中字符串类型之间的转换**

有时需要将不同类(如 string、StringBuffer、StringBuilder)的字符串对象相互转换。以下是做同样事情的一些技巧。让我们覆盖以下所有用例:

1.  从字符串到字符串缓冲区和字符串构建器
2.  从字符串缓冲区和字符串构建器到字符串
3.  从 StringBuffer 到 StringBuilder，反之亦然

**案例 1:** 从 String 到 StringBuffer 和 String builder**T3】**

这是一个简单的方法，因为我们可以直接将字符串类对象传递给字符串缓冲区和字符串构建器类构造函数。由于字符串类在 java 中是不可变的，所以对于编辑字符串，我们可以通过将其转换为 StringBuffer 或 StringBuilder 类对象来执行同样的操作。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate conversion from
// String to StringBuffer and StringBuilder

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "Geeks";

        // Converting String object to StringBuffer object
        // by
        // creating object of StringBuffer class
        StringBuffer sbr = new StringBuffer(str);

        // Reversing the string
        sbr.reverse();

        // Printing the reversed string
        System.out.println(sbr);

        // Converting String object to StringBuilder object
        StringBuilder sbl = new StringBuilder(str);

        // Adding it to string using append() method
        sbl.append("ForGeeks");

        // Print and display the above appended string
        System.out.println(sbl);
    }
}
```

**Output**

```java
skeeG
GeeksForGeeks
```

**情况 2:** 从 StringBuffer 和 StringBuilder 到 String

这种转换可以使用 ***到字符串()*** **方法**来执行，该方法在 StringBuffer 和 StringBuilder 类中都被覆盖。
下面是 java 程序来演示一下。注意，当我们使用 *toString()* 方法时，一个新的 String 对象(在 Heap 区域)被分配并初始化为当前由 StringBuffer 对象表示的字符序列，这意味着对 StringBuffer 对象的后续更改不会影响 String 对象的内容。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Conversion from
// String to StringBuffer and StringBuilder

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating objects of StringBuffer class
        StringBuffer sbr = new StringBuffer("Geeks");
        StringBuilder sbdr = new StringBuilder("Hello");

        // Converting StringBuffer object to String
        // using toString() method
        String str = sbr.toString();

        // Printing the above string
        System.out.println(
            "StringBuffer object to String : ");
        System.out.println(str);

        // Converting StringBuilder object to String
        String str1 = sbdr.toString();

        // Printing the above string
        System.out.println(
            "StringBuilder object to String : ");
        System.out.println(str1);

        // Changing StringBuffer object sbr
        // but String object(str) doesn't change
        sbr.append("ForGeeks");

        // Printing the above two strings on console
        System.out.println(sbr);
        System.out.println(str);
    }
}
```

**Output**

```java
StringBuffer object to String : 
Geeks
StringBuilder object to String : 
Hello
GeeksForGeeks
Geeks
```

**情况 3:** 从 StringBuffer 到 StringBuilder，反之亦然

这种转换很棘手。没有直接的方法来转换相同的。在这种情况下，我们可以使用一个字符串类对象。我们首先使用 ***将 StringBuffer/StringBuilder 对象转换为 String，然后使用构造函数将 String 从 String 转换为 StringBuilder/StringBuffer。***

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Demonstrate conversion from
// String to StringBuffer and StringBuilder

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of StringBuffer class and
        // passing our input string to it
        StringBuffer sbr = new StringBuffer("Geeks");

        // Storing value StringBuffer object in String and
        // henceforth converting StringBuffer object to
        // StringBuilder class
        String str = sbr.toString();
        StringBuilder sbl = new StringBuilder(str);

        // Printing th StringBuilder object on console
        System.out.println(sbl);
    }
}
```

**Output**

```java
Geeks
```

从以上三个用例中，我们可以得出以下结论:

*   String 的对象是不可变的，StringBuffer 和 StringBuilder 的对象是可变的。
*   StringBuffer 和 StringBuilder 类似，但是对于单线程程序来说，StringBuffer 比 StringBuffer 更快，也更受欢迎。如果需要线程安全，那么使用 StringBuffer。

**相关文章:** [爪哇倒一弦(5 种不同方式)](https://www.geeksforgeeks.org/reverse-a-string-in-java-5-different-ways/)
本文由**普拉加尔和高拉夫·米格拉尼**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
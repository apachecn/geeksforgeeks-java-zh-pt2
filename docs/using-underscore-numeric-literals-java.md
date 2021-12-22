# 在 Java 的数值文字中使用下划线

> 原文:[https://www . geesforgeks . org/using-下划线-数字-文字-java/](https://www.geeksforgeeks.org/using-underscore-numeric-literals-java/)

在引入 Java 时，不允许在数字文字中使用下划线，但是从 Java 1.7 版本开始，我们可以在数字文字的数字之间使用“_”下划线符号。您只能将下划线放在数字之间。请记住，我们不能在某些地方放置下划线，如下所示:

*   At the beginning or end of a number
*   In floating-point text
*   Near the decimal point of, after F or L.
*   Before, where a string of numbers was needed
*   We can only use underscores between numbers, otherwise we will get compile-time errors.

让我们讨论插图，以证明上述说法如下:

**说明 1:** 数字文字中下划线的有效用法

```java
Input  : int i = 12_34_56; 
Output : 123456

Input  : double db = 1_2_3.4_5_6
Output : 123.456
```

**说明 2:** 数值文字中的无效用法

```java
int i = _12345; // Invalid as this is an identifier, not a numeric literal
```

```java
double db = 123._456; // Invalid as we cannot put underscores adjacent to a decimal point
```

```java
double db 123_.456_; // Invalid as we cannot put underscores at the end of a number 
```

现在 geek 你一定想知道为什么会引入它，所以基本上这种方法的主要优点是代码的可读性会得到提高。编译时，这些下划线符号将被自动删除。我们也可以在数字之间使用多个下划线符号。例如，下面是一个有效的数字文字，如下所示:

```java
int x4 = 5_______2;        // OK (decimal literal)
```

**实现:**在编写代码之前，确保我们确实有 java 版及更高版本，正如 header 本身所讨论的。为了检查，打开终端，写下命令，如果不是这样，安装最新的 java 版本，如果已经更新，我们就可以走了。

```java
java -version  
```

**示例:**

## Java

```java
// Java program to illustrate
// using underscore in Numeric Literals

// Main class
// UnderScoreSymbols
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initialiing numeric literals
        int i = 12_34_5_6;
        double db = 1_23.45_6;
        // Literal with underscore
        int x4 = 5_______2;

        // Simply printing and displaying above literals
        System.out.println("i = " + i);
        System.out.println("db = " + db);
        System.out.println("x4 = " + x4);
    }
}
```

**输出**

```java
i = 123456
db = 123.456
x4 = 52
```

本文由 **Shivakant Jaiswal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
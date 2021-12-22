# 在 Java 的数值文字中使用下划线

> 原文:[https://www . geesforgeks . org/使用 java 中的数字文字下划线/](https://www.geeksforgeeks.org/using-underscore-in-numeric-literals-in-java/)

JDK 7 引入了一个新特性，允许使用下划线字符书写数字。基本上，它们被打破以增强可读性。这个特性使我们能够将数字文字中的数字分组，这提高了代码的可读性。例如，如果我们的代码包含具有许多数字的数字，我们可以使用下划线字符来分隔三个一组的数字，类似于我们使用逗号或空格等标点符号作为分隔符。让我们用一个例子进一步探讨

**示例**

## Java

```java
// Java Program to Illustrate Diggerent Ways of Usage
// of Underscore in Numeric Literals

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws java.lang.Exception
    {

        // Declaring and initializing values of
        // integer, long, float and double datatype

        // Integer literal
        int inum = 1_00_00_000;
        // Long literal
        long lnum = 1_00_00_000;
        // Float literal
        float fnum = 2.10_001F;
        // Double literal
        double dnum = 2.10_12_001;

        // Printing and displaying values on console
        System.out.println("inum:" + inum);
        System.out.println("lnum:" + lnum);
        System.out.println("fnum:" + fnum);
        System.out.println("dnum:" + dnum);
    }
}
```

**输出**

```java
inum:10000000
lnum:10000000
fnum:2.10001
dnum:2.1012001
```

本文由**闪烁泰亚吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
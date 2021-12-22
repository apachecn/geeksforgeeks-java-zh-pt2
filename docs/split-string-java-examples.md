# Java 中的 Split() String 方法，带示例

> 原文:[https://www.geeksforgeeks.org/split-string-java-examples/](https://www.geeksforgeeks.org/split-string-java-examples/)

**字符串 split()** 方法在给定正则表达式的匹配项周围断开给定的字符串。根据给定的正则表达式进行拆分后，此方法返回一个 char 数组。

**例:**

```java
Input String: 016-78967
Regular Expression: - 
Output : {"016", "78967"}
```

以下是 Java 中 split()方法的两种变体:

### **1。公共字符串[ ]拆分(字符串正则表达式，int 限制)**

**参数:**

*   正则表达式——定界正则表达式
*   极限–最终阈值

**返回:**通过拆分给定的字符串来计算字符串数组。

**抛出:** *模式同步异常*–如果提供的正则表达式语法无效。

**极限参数可以有 3 个值:**

*   **限制>0–**如果是这种情况，那么模式最多应用限制-1 次，结果数组的长度将不超过 n，并且结果数组的最后一个条目将包含最后一个匹配模式之外的所有输入。
*   **限制<0–**在这种情况下，模式将被应用尽可能多的次数，并且得到的数组可以是任何大小。
*   **limit = 0–**在这种情况下，模式将被应用尽可能多的次数，结果数组可以是任何大小，尾随的空字符串将被丢弃。

**下面是它的工作原理:**

让将要被拆分的字符串是–**geek ss @ for @ geek ss**

<figure class="table">T10】RegexT20】@ 【极客】}T52】sT56】{“极客”、“、“”、“”、“}

| 限制 | 结果 |
| --- | --- |
| Two | {“极客 ss”，“代表@极客 ss”} |
| s | five | {"Geek", ","@ is @ Geek ",",","}. |
| -2 |
| s | 0【T60 |

</figure>

*以下是演示 split()*

**工作原理的 Java 示例代码示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split(regex,
// limit) with small limit.
public class GFG {
    public static void main(String args[])
    {
        String str = "geekss@for@geekss";
        String[] arrOfStr = str.split("@", 2);

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
geekss
for@geekss
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split(regex,
// limit) with high limit.
public class GFG {
    public static void main(String args[])
    {
        String str = "geekss@for@geekss";
        String[] arrOfStr = str.split("@", 5);

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
geekss
for
geekss
```

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split(regex,
// limit) with negative limit.
public class GFG {
    public static void main(String args[])
    {
        String str = "geekss@for@geekss";
        String[] arrOfStr = str.split("@", -2);

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
geekss
for
geekss
```

**例 4:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split(regex,
// limit) with high limit.
public class GFG {
    public static void main(String args[])
    {
        String str = "geekss@for@geekss";
        String[] arrOfStr = str.split("s", 5);

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
geek

@for@geek
```

**例 5:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split(regex,
// limit) with negative limit.
public class GFG {
    public static void main(String args[])
    {
        String str = "geekss@for@geekss";
        String[] arrOfStr = str.split("s", -2);

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
geek

@for@geek
```

**例 6:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split(regex,
// limit) with 0 limit.
public class GFG {
    public static void main(String args[])
    {
        String str = "geekss@for@geekss";
        String[] arrOfStr = str.split("s", 0);

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
geek

@for@geek
```

### **2。公共字符串[]拆分(字符串正则表达式)**

这个 split 方法的变体将正则表达式作为参数，并在这个正则表达式正则表达式的匹配项周围断开给定的字符串。这里，默认限制为 0。

**参数:** *正则表达式*–一个定界正则表达式

**返回:**通过拆分给定的字符串来计算字符串数组。

**抛出:** *模式同步异常*–如果提供的正则表达式语法无效。

以下是一些工作示例代码:

**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split()
public class GFG {
    public static void main(String args[])
    {
        String str = "GeeksforGeeks:A Computer Science Portal";
        String[] arrOfStr = str.split(":");

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
GeeksforGeeks
A Computer Science Portal
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split()
public class GFG {
    public static void main(String args[])
    {
        String str = "GeeksforGeeksforStudents";
        String[] arrOfStr = str.split("for");

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
Geeks
Geeks
Students
```

在上例中可以看到，模式/正则表达式“for”被应用了两次(因为“for”在要拆分的字符串中出现了两次)

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split()
public class GFG {
    public static void main(String args[])
    {
        String str = "Geeks for Geeks";
        String[] arrOfStr = str.split(" ");

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
Geeks
for
Geeks
```

**例 4:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split()
public class GFG {
    public static void main(String args[])
    {
        String str = "Geekssss";
        String[] arrOfStr = str.split("s");

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
Geek
```

在上面的例子中，尾随的空字符串不包含在结果数组 arrOfStr 中。

**例 5:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split()
public class GFG {
    public static void main(String args[])
    {
        String str = "GeeksforforGeeksfor   ";
        String[] arrOfStr = str.split("for");

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
Geeks

Geeks

```

在上面的例子中，尾随空格(因此不是空字符串)成为结果数组 arrOfStr 中的一个字符串。

**例 6:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of split()
// using regular expressions
public class GFG {
    public static void main(String args[])
    {
        String str = "word1, word2 word3@word4?word5.word6";
        String[] arrOfStr = str.split("[, ?.@]+");

        for (String a : arrOfStr)
            System.out.println(a);
    }
}
```

**Output**

```java
word1
word2
word3
word4
word5
word6
```

在上面的示例中，每当遇到集合中指定的任一字符时，单词都会被分隔开。

本文由 **Vaibhav Bajpai** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 使用正则表达式

打印字符串中每个单词的第一个字母

> 原文:[https://www . geesforgeks . org/print-first-letter-word-string-use-regex/](https://www.geeksforgeeks.org/print-first-letter-word-string-using-regex/)

给定一个字符串，提取其中每个单词的第一个字母。“单词”被定义为字母字符的连续串，即任何大写或小写字符 a-z 或 A-Z

示例:

```java
Input : Geeks for geeks
Output :Gfg

Input : United Kingdom
Output : UK

```

下面是[正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)提取每个单词的第一个字母。它使用'/b '(边界匹配器之一)。请参考[如何写正则表达式？](https://www.geeksforgeeks.org/write-regular-expressions/)要学会它。

```java
\b[a-zA-Z]

```

```java
// Java program to demonstrate extracting first
// letter of each word using Regex

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Test 
{
    public static void main(String[] args) 
    {
        String s1 = "Geeks for Geeks";
        String s2 = "A Computer Science Portal for Geeks";

        Pattern p = Pattern.compile("\\b[a-zA-Z]");

        Matcher m1 = p.matcher(s1);
        Matcher m2 = p.matcher(s2);

        System.out.println("First letter of each word from string \"" + s1 + "\" : ");
        while (m1.find())
            System.out.print(m1.group());

        System.out.println();

        System.out.println("First letter of each word from string \"" + s2 + "\" : ");

        while (m2.find()) 
            System.out.print(m2.group());

    }
}
```

输出:

```java
First letter of each word from string "Geeks for Geeks" : 
GfG
First letter of each word from string "A Computer Science Portal for Geeks" : 
ACSPfG

```

**下一篇文章:** [使用 Java 中的正则表达式从字符串中提取每个单词](https://www.geeksforgeeks.org/extracting-word-string-java/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
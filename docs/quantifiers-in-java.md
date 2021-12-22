# Java 中的量词

> 原文:[https://www.geeksforgeeks.org/quantifiers-in-java/](https://www.geeksforgeeks.org/quantifiers-in-java/)

**先决条件:**[Java 中的正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)

Java 中的量词允许用户指定匹配的出现次数。下面是 Java 中一些常用的量词。

```java
X*        Zero or more occurrences of X
X?        Zero or One occurrences of X
X+        One or More occurrences of X
X{n}      Exactly n occurrences of X 
X{n, }    At-least n occurrences of X
X{n, m}   Count of occurrences of X is from n to m
```

上面的量词可以是贪婪的、不情愿的和占有欲的。

### 贪婪量词(默认)

默认情况下，量词是贪婪的。贪婪的量词试图匹配匹配给定模式的最长文本。贪婪量词的工作原理是在尝试任何匹配之前先读取整个字符串。如果整个文本不匹配，请删除最后一个字符，然后重试，重复该过程，直到找到匹配项。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate Greedy Quantifiers

import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Test
{
    public static void main(String[] args)
    {
        // Making an instance of Pattern class
        // By default quantifier "+" is Greedy
        Pattern p = Pattern.compile("g+");

        // Making an instance of Matcher class
        Matcher m = p.matcher("ggg");

        while (m.find())
            System.out.println("Pattern found from " + m.start() +
                               " to " + (m.end()-1));

    }
}
```

**Output**

```java
Pattern found from 0 to 2
```

**说明:**模式 **g+** 表示 **g** 的一次或多次出现。文字为 **ggg** 。贪婪匹配器将匹配最长的文本，即使匹配文本的部分也匹配。本例中 **g** 和 **gg** 也匹配，但是贪婪的匹配者产生 **ggg** 。

### 不情愿的量词(附加？量词之后)

这个量词使用了与贪婪量词相反的方法。它从第一个字符开始，一次处理一个字符。

## 爪哇

```java
// Java program to demonstrate Reluctant Quantifiers

import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Test
{
    public static void main(String[] args)
    {
        // Making an instance of Pattern class
        // Here "+" is a Reluctant quantifier because
        // a "?' is appended after it.
        Pattern p = Pattern.compile("g+?");

        // Making an instance of Matcher class
        Matcher m = p.matcher("ggg");

        while (m.find())
            System.out.println("Pattern found from " + m.start() +
                               " to " + (m.end()-1));

    }
}
```

**输出**

```java
Pattern found from 0 to 0
Pattern found from 1 to 1
Pattern found from 2 to 2
```

**解释:**由于量词不情愿，所以将测试中最短的部分与模式匹配。它一次处理一个字符。

### 所有格量词(在量词后面附加一个+)

这个量词匹配尽可能多的字符，就像一个贪婪的量词。但是如果整个字符串不匹配，那么它不会尝试从末尾删除字符。

## 爪哇

```java
// Java program to demonstrate Possessive Quantifiers

import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Test
{
    public static void main(String[] args)
    {
        // Making an instance of Pattern class
        // Here "+" is a Possessive quantifier because
        // a "+' is appended after it.
        Pattern p = Pattern.compile("g++");

        // Making an instance of Matcher class
        Matcher m = p.matcher("ggg");

        while (m.find())
            System.out.println("Pattern found from " + m.start() +
                               " to " + (m.end()-1));
    }
}
```

**输出**

```java
Pattern found from 0 to 2
```

**解释:**我们得到和 Greedy 一样的输出，因为整个文本都和模式匹配。

### 贪婪量词和所有格量词的区别

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate difference
// between Possessive and Greedy Quantifiers

import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Test
{
    public static void main(String[] args)
    {
        // Create a pattern with Greedy quantifier
        Pattern pg = Pattern.compile("g+g");

        // Create same pattern with possessive quantifier
        Pattern pp = Pattern.compile("g++g");        

        System.out.println("Using Greedy Quantifier");
        Matcher mg = pg.matcher("ggg");
        while (mg.find())
            System.out.println("Pattern found from " + mg.start() +
                               " to " + (mg.end()-1));

        System.out.println("\nUsing Possessive Quantifier");
        Matcher mp = pp.matcher("ggg");
        while (mp.find())
            System.out.println("Pattern found from " + mp.start() +
                               " to " + (mp.end()-1));

    }
}
```

**Output**

```java
Using Greedy Quantifier
Pattern found from 0 to 2

Using Possessive Quantifier
```

在上面的例子中，由于第一个量词是贪婪的， **g+** 匹配整个字符串。如果我们将 **g+** 与整串匹配， **g+g** 不匹配，贪婪量词去掉最后一个字符，将 **gg** 与 **g+** 匹配，找到匹配。在所有格量词中，我们开始喜欢贪婪。 **g+** 匹配整串，但 **g+** 匹配整串与 **g+g** 不匹配 **ggg** 。不像 Greedy，由于量词是所有格，我们就此打住。

本文由**拉胡尔·阿加瓦尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
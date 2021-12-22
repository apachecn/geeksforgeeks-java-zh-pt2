# Java 中的正则表达式

> 原文:[https://www.geeksforgeeks.org/regular-expressions-in-java/](https://www.geeksforgeeks.org/regular-expressions-in-java/)

正则表达式(简称 Regex)是一个定义字符串模式的应用编程接口，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是字符串的几个领域，Regex 被广泛用于定义约束。正则表达式在 java.util.regex 包下提供。这包括 3 个类和 1 个接口。**Java . util . regex**包主要由以下三个类组成，如下表所示:

<figure class="table">对文本执行匹配操作

| kind | describe |
| --- | --- |
| 乌提尔。regex。模式 | Used to define patterns. |
| 不，不，不。瑞吉斯。匹配项 | Used for usage mode |

</figure>

**Java 中的 Regex 为我们提供了下面列出的两个类:**

1.  模式类
2.  火柴人班

更多的理解可以从下面提供的图片中理解如下:

![](img/71c19a42eb04c1ed9a20215bb814ac98.png)

**类 1:** 模式类

此类是正则表达式的编译，可用于定义各种类型的模式，不提供公共构造函数。这可以通过调用 compile()方法来创建，该方法接受正则表达式作为第一个参数，从而在执行后返回一个模式。

<figure class="table">

| way | describe |
| --- | --- |
| 编译(字符串正则表达式) | It is used to compile a given regular expression into a pattern. |
| 年复一年(regex 字符串，int flags) | Used to compile a given regular expression into a pattern with a given flag. |
| 旗帜() | The matching flag used to return the pattern. |
| 匹配器(字符序列输入) | It is used to create a matcher that will match the given input according to the pattern. |
| 匹配(字符串正则表达式，字符序列输入) | It is used to compile the given regular expression and try to match the given input with it. |
| model | Returns the regular expression used to compile the pattern. |
| quote | The text pattern string used to return the specified string. |
| 拆分(字符序列输入) | Used to split the given input sequence around the matches of the pattern. |
| 拆分(CharSequence 输入，int 限制) | Used to split the given input sequence around the matches of the pattern. Limit the number of times the parameter controls the application mode. |
| toString() | It is used to return the string representation of this pattern. |

</figure>

**示例:**模式类

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrating Working of matches() Method
// Pattern class

// Importing Pattern class from java.util.regex package
import java.util.regex.Pattern;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Following line prints "true" because the whole
        // text "geeksforgeeks" matches pattern
        // "geeksforge*ks"
        System.out.println(Pattern.matches(
            "geeksforge*ks", "geeksforgeeks"));

        // Following line prints "false" because the whole
        // text "geeksfor" doesn't match pattern "g*geeks*"
        System.out.println(
            Pattern.matches("g*geeks*", "geeksfor"));
    }
}
```

**Output**

```
true
false
```

**2 级:**火柴人级

该对象用于在 java 中对输入字符串执行匹配操作，从而解释前面解释的模式。这也没有定义公共构造函数。这可以通过在任何模式对象上调用 matcher()来实现。

<figure class="table">

| way | describe |
| --- | --- |
| 查找() | It is mainly used to search for regular expressions that appear many times in text. |
| 查找(int start) | Used to search for the occurrence of regular expressions in text from a given index. |
| 【开始()】 | Gets the starting index of the match found using the find () method. |
| end() | Gets the ending index of the match found using the find () method. It returns the character index next to the last matching character. |
| 组计数() | Total number of matching subsequences used to find. |
| Group () | Used to find matching subsequences. |
| matching | Used to test whether the regular expression matches the pattern. |

</figure>

> **注意:【Pattern.matches()检查整个文本是否与模式匹配。其他方法(如下所示)主要用于查找文本中模式的多次出现。**

让我们像讨论模式类一样讨论几个示例程序。为了更好地理解 Matcher 类，这里我们将讨论几个演示 compile()、find()、start()、end()和 split()工作原理的 java 程序。

**示例 1:** 模式搜索

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of
// String matching in Java

// Importing Matcher and Pattern class to
//
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Create a pattern to be searched
        // Custom pattern
        Pattern pattern = Pattern.compile("geeks");

        // Search above pattern in "geeksforgeeks.org"
        Matcher m = pattern.matcher("geeksforgeeks.org");

        // Finding string using find() method
        while (m.find())

            // Print starting and ending indexes
            // of the pattern in the text
            // using this functionality of this class
            System.out.println("Pattern found from "
                               + m.start() + " to "
                               + (m.end() - 1));
    }
}
```

**Output**

```
Pattern found from 0 to 4
Pattern found from 8 to 12
```

**示例 2:** 简单正则表达式搜索

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of
// String matching in Java

// Importing Matcher and Pattern class
// from java.util package
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating a pattern to be searched
        // Custom pattern to be searched
        Pattern pattern = Pattern.compile("ge*");

        // Searching for the above pattern in
        // "geeksforgeeks.org"
        Matcher m = pattern.matcher("geeksforgeeks.org");

        // Checking whether the pattern is there or not
        // using find() method
        while (m.find())

            // Print starting and ending indexes of the
            // pattern in text using method functionality of
            // this class
            System.out.println("Pattern found from "
                               + m.start() + " to "
                               + (m.end() - 1));
    }
}
```

**Output**

```
Pattern found from 0 to 2
Pattern found from 8 to 10
Pattern found from 16 to 16
```

**示例 3:** 不区分大小写的模式搜索

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrating Working of String matching

// Importing Matcher class and Pattern classes
// from java.util.regex package
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating a pattern to be searched
        Pattern pattern = Pattern.compile(
            "ge*", Pattern.CASE_INSENSITIVE);

        // Searching above pattern in "geeksforgeeks.org"
        Matcher m = pattern.matcher("GeeksforGeeks.org");

        // Find th above string using find() method
        while (m.find())

            // Printing the starting and ending indexes of
            // the pattern in text using class method
            // functionalities
            System.out.println("Pattern found from "
                               + m.start() + " to "
                               + (m.end() - 1));
    }
}
```

**Output**

```
Pattern found from 0 to 2
Pattern found from 8 to 10
Pattern found from 16 to 16
```

**示例 4:** [split()方法](https://www.geeksforgeeks.org/split-string-java-examples/)根据分隔符模式拆分文本。

string split()方法在给定正则表达式的匹配项周围断开给定的字符串。这种方法有两种变体，所以在开始实现这种方法之前一定要仔细研究一下。

插图:

```
Input  --> String: 016-78967
Output -->  Regex: {"016", "78967"}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program Illustrating Working of split() Method
// by Splitting a text by a given pattern

// Importing Matcher and Pattern classes from
// java.util.regex package
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Custom string
        String text = "geeks1for2geeks3";

        // Specifies the string pattern
        // which is to be searched
        String delimiter = "\\d";
        Pattern pattern = Pattern.compile(
            delimiter, Pattern.CASE_INSENSITIVE);

        // Used to perform case insensitive search of the
        // string
        String[] result = pattern.split(text);

        // Iterating using for each loop
        for (String temp : result)
            System.out.println(temp);
    }
}
```

**Output**

```
geeks
for
geeks
```
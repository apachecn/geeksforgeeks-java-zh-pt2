# 在 Java 中使用 Regex 移除空格

> 原文:[https://www . geesforgeks . org/remove-white spaces-use-regex-in-Java/](https://www.geeksforgeeks.org/removing-whitespaces-using-regex-in-java/)

给定一个字符串，您的任务是使用 Java 正则表达式删除字符串中的空格。

**示例**

```java
Input :    Hello   Everyone . 
Output : HelloEveryone.

Input :   Geeks  for  Geeks    .
Output : GeeksforGeeks.
```

### 正则表达式

正则表达式或正则表达式是一个定义字符串模式的应用编程接口，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是字符串的几个领域，Regex 被广泛用于定义约束。正则表达式在 **java.util.regex** 包下提供。

### 方法

在 Java 中，有许多方法可以使用 Regex 删除字符串中的空格。下面列出了其中的一些。

*   使用 Regex。Matcher.replaceAll()方法
*   使用 appendReplacement()方法

### 1.使用 Matcher.replaceAll()方法

[**方法用给定的替换字符串替换输入序列中与模式匹配的每个子序列。**](https://www.geeksforgeeks.org/matcher-replaceallstring-method-in-java-with-examples/)

**申报:**

```java
public String replaceAll(String replacement) 
```

**参数:**替换–替换字符串。

**返回值:**字符串通过用替换字符串替换每个匹配的子序列来构造，根据需要替换捕获的子序列。

下面的程序演示了如何使用 [util.regex.Pattern](https://www.geeksforgeeks.org/regular-expressions-in-java/) 类的 matcher.replaceAll(字符串替换)方法删除空格。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to remove whitespaces from a string
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class GeeksforGeeks {

    public static String removeWhite(String s) {

        // Creating a pattern for whitespaces
        Pattern patt = Pattern.compile("[\\s]");

        // Searching patt in s.
        Matcher mat = patt.matcher(s);

        // Replacing
        return mat.replaceAll("");
   }

    public static void main(String[] argv)
    {
        String s = "   Hello  Geeks  .  ";
        System.out.println(removeWhite(s));
    }
}
```

**Output**

```java
HelloGeeks.
```

### 2.使用 appendReplacement()方法

**匹配器类**的 [**追加替换(StringBuilder，String)**](https://www.geeksforgeeks.org/matcher-appendreplacementstringbuilder-string-method-in-java-with-examples/) 方法表现为追加替换方法。此方法读取输入字符串，并用匹配器字符串中匹配的模式替换它。

**语法:**

```java
public Matcher appendReplacement(StringBuilder builder, String stringToBeReplaced)
```

**参数:**该方法取两个参数:

*   **builder** :存储目标字符串的 StringBuilder。
*   **字符串替换**:匹配器中要替换的字符串。

**返回值:**该方法返回一个替换了目标字符串的**匹配器**。

**异常:**该方法抛出以下异常:

*   **illegalstatexception**:如果还没有尝试匹配，或者如果之前的匹配操作失败。
*   **IllegalArgumentException** :如果替换字符串引用了模式中不存在的命名捕获组。
*   **IndexOutOfBoundsException**:如果替换字符串引用了模式中不存在的捕获组。

下面的程序演示了如何使用 [util.regex.Pattern](https://www.geeksforgeeks.org/regular-expressions-in-java/) 类的 matcher . append replacement(StringBuilder builder，String stringtobereplacement)方法删除空格。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to remove the whiltespaces
// in a string using Java Regex
import java.util.regex.Matcher;
import java.util.regex.Pattern;

class GFG {
    public static void main (String[] args) {

          String input = "   Geeks    for   Geeks  ";

          String regex = "\\s";
          String constants = "";

          // Creating a pattern object
          Pattern pattern = Pattern.compile(regex);

          // Matching the compiled pattern in the String
          Matcher matcher = pattern.matcher(input);

          // Creating an empty string buffer
          StringBuffer sb = new StringBuffer();

          while (matcher.find()) {
            constants = constants+matcher.group();
            matcher.appendReplacement(sb, "");
          }
      matcher.appendTail(sb);
      System.out.println(sb.toString()+constants);
    }
}
```

**Output**

```java
GeeksforGeeks            
```
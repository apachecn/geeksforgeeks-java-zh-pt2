# Java 中的 Regex 边界匹配器

> 原文:[https://www . geesforgeks . org/regex-border-matchers-in-Java/](https://www.geeksforgeeks.org/regex-boundary-matchers-in-java/)

先决条件-[Java 中的正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)

边界匹配可以帮助我们找到字符串匹配发生的位置。通过用边界匹配器指定这样的信息，可以使模式匹配更加精确。例如，也许你对找到一个特定的单词感兴趣，但前提是它出现在一行的开头或结尾。或者你可能想知道匹配是发生在单词边界上，还是在上一次匹配结束时。

**边界匹配者列表** 

*   ^**–**放在要匹配的单词之前
*   $**–**放在要匹配的单词末尾
*   \ b**–**检查模式是在单词边界开始还是结束
*   \ B**–**匹配非单词边界上的表达式
*   \ A**–**输入的开始
*   \ G**–**要求只在前一场比赛结束时才进行比赛
*   \ Z**–**输入的结束，但对于最终的结束符，如果有的话
*   \z **—** 输入结束

**情况 1:将单词与^和$** 匹配

*   **^**–匹配一行的开头
*   **$**–匹配结束。

*   ```java
    Input : txt = "geeksforgeeks", regex = "^geeks"
    Output : Found from index 0 to 3
    Explanation : Note that the result doesn't include "geeks" after
                  "for" as we have used ^ in regex.
    ```

*   ```java
    Input : txt = "geeksforgeeks", regex = "geeks{content}quot;
    Output : Found from index 8 to 13.
    Explanation : Note that the result doesn't include "geeks" before 
                 "for" as we have used $ in regex.
    ```

*   ```java
    Input : txt = "geeksforgeeks", regex = "^geeks{content}quot;
    Output : No match found
    Explanation : The given regex would only matches with "geeks".
    ```

*   ```java
    Input : txt = "  geeksforgeeks", regex = "^geeks"
    Output: No match found.
    Explanation : The input string contains extra whitespace at the beginning.
    ```

*   ```java
    // Extra \ is used to escape one \
    Input : txt = "  geeksforgeeks", regex : "^\\s+geeks"
    Output: Found from index 0 to 6.
    Explanation : The pattern specifies geeks after one or more spaces.
    ```

```java
// Java program to demonstrate that ^ matches the beginning of
// a line, and $ matches the end.
import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Reg
{
    public static void main(String[] args)
    {
        String txt = "geeksforgeeks";

        // Demonstrating ^
        String regex1 = "^geeks";
        Pattern pattern1 = Pattern.compile(regex1, Pattern.CASE_INSENSITIVE);
        Matcher matcher1 = pattern1.matcher(txt);
        while (matcher1.find())
        {
            System.out.println("Start index: " + matcher1.start());
            System.out.println("End index: " + matcher1.end());
        }

        // Demonstrating $
        String regex2 = "geeks{content}quot;;
        Pattern pattern2 = Pattern.compile(regex2, Pattern.CASE_INSENSITIVE);
        Matcher matcher2 = pattern2.matcher(txt);
        while (matcher2.find())
        {
            System.out.println("\nStart index: " + matcher2.start());
            System.out.println("End index: " + matcher2.end());
        }
    }
}
```

输出:

```java
Start index: 0
End index: 5

Start index: 8
End index: 13

```

****情况 2:使用\b**** 检查模式是在单词边界开始还是结束

*   ```java
    Input: txt = "geeksforgeeks geekspractice", pat = "\\bgeeks"
    Output: Found from index 0 to 5 and from index 14 to 19
    Explanation : The pattern "geeks" is present at the beginning
                  of two words "geeksforgeeks" and "geekspractice"

    ```

*   ```java
    Input: txt = "geeksforgeeks geekspractice", pat = "geeks\\b"
    Output: Found from index 8 to 13
    Explanation : The pattern "geeks" is present at the end of one
                  word "geeksforgeeks"

    ```

```java
// Java program to demonstrate use of \b to match 
// regex at beginning and end of word boundary 
import java.util.regex.Matcher; 
import java.util.regex.Pattern; 

class Reg 
{ 
    public static void main(String[] args) 
    { 
        String txt = "geeksforgeeks geekspractice"; 

        // Demonstrating beginning of word boundary 
        String regex1 = "\\bgeeks"; // Matched at two places 
        Pattern pattern1 = Pattern.compile(regex1, Pattern.CASE_INSENSITIVE); 
        Matcher matcher1 = pattern1.matcher(txt); 
        while (matcher1.find()) 
        { 
            System.out.println("Start index: " + matcher1.start()); 
            System.out.println("End index: " + matcher1.end()); 
        } 

        // Demonstrating end of word boundary 
        String regex2 = "geeks\\b"; // Matched at one place 
        Pattern pattern2 = Pattern.compile(regex2, Pattern.CASE_INSENSITIVE); 
        Matcher matcher2 = pattern2.matcher(txt); 
        while (matcher2.find()) 
        { 
            System.out.println("\nStart index: " + matcher2.start()); 
            System.out.println("End index: " + matcher2.end()); 
        } 
    } 
} 
```

输出:

```java
Start index: 0
End index: 5
Start index: 14
End index: 19

Start index: 8
End index: 13

```

****例 3:在非单词边界上匹配表达式，用\B 代替**** 

*   ```java
    Input: txt = "geeksforgeeks geekspractice", pat = "\\Bgeeks"
    Output: Found from index 8 to 13
    Explanation : One occurrence  of pattern "geeks" is not present at
                  the beginning of word which is end of "geeksforgeeks"

    ```

*   ```java
    Input: txt = "geeksforgeeks geekspractice", pat = "geeks\\B"
    Output: Found from index 0 to 5 and from index 14 to 19
    Explanation : Two occurrences of "geeks" are not present at the end
                  of word.

    ```

```java
// Java program to demonstrate use of \B to match 
// regex at beginning and end of non word boundary 
import java.util.regex.Matcher; 
import java.util.regex.Pattern; 

class Reg 
{ 
    public static void main(String[] args) 
    { 
        String txt = "geeksforgeeks geekspractice"; 

        // Demonstrating Not beginning of word 
        String regex1 = "\\Bgeeks"; // Matches with two 
        Pattern pattern1 = Pattern.compile(regex1, Pattern.CASE_INSENSITIVE); 
        Matcher matcher1 = pattern1.matcher(txt); 
        while (matcher1.find()) 
        { 
            System.out.println("Start index: " + matcher1.start()); 
            System.out.println("End index: " + matcher1.end() + "\n"); 
        } 

        // Demonstrating Not end of word 
        String regex2 = "geeks\\B"; // Matches with one 
        Pattern pattern2 = Pattern.compile(regex2, Pattern.CASE_INSENSITIVE); 
        Matcher matcher2 = pattern2.matcher(txt); 
        while (matcher2.find()) 
        { 
            System.out.println("Start index: " + matcher2.start()); 
            System.out.println("End index: " + matcher2.end()); 
        } 
    } 
} 
```

输出:

```java
Start index: 8
End index: 13

Start index: 0
End index: 5
Start index: 14
End index: 19

```

**情况 4:匹配只在前一场比赛结束时发生，使用\G:** 

*   ```java
    Input: txt = "geeksgeeks geeks", pat = "\\Ggeeks"
    Output: Found from index 0 to 5 and from 5 to 10
    Explanation : Only first two occurrences of "geeks" in text
                  match. the occurrence after space doesn't match
                  as it is not just after previous match.

    ```

```java
// Java program to demonstrate use of \G to match 
// to occur only at the end of the previous match 
import java.util.regex.Matcher; 
import java.util.regex.Pattern; 

class Reg 
{ 
    public static void main(String[] args) 
    { 
        String txt = "geeksgeeks geeks"; 

        // Demonstrating \G 
        String regex1 = "\\Ggeeks"; // Matches with first two geeks 
        Pattern pattern1 = Pattern.compile(regex1, Pattern.CASE_INSENSITIVE); 
        Matcher matcher1 = pattern1.matcher(txt); 
        while (matcher1.find()) 
        { 
            System.out.println("Start index: " + matcher1.start()); 
            System.out.println("End index: " + matcher1.end()); 
        } 
    } 
} 
```

输出:

```java
Start index: 0
End index: 5
Start index: 5
End index: 10

```

**参考文献:**[https://docs . Oracle . com/javase/tutorial/essential/regex/bounds . html](https://docs.oracle.com/javase/tutorial/essential/regex/bounds.html)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
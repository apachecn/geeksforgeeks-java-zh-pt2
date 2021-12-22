# 在 Java 中删除字符串的前导零

> 原文:[https://www . geesforgeks . org/remove-training-zero-string-Java/](https://www.geeksforgeeks.org/remove-trailing-zeros-string-java/)

给定一串数字，去掉前导零。

示例:

```java
Input : 00000123569
Output : 123569

Input : 000012356090
Output : 12356090

```

我们使用 [StringBuffer](https://www.geeksforgeeks.org/g-fact-27-string-vs-stringbuilder-vs-stringbuffer/) 类作为[字符串是不可变的](https://www.geeksforgeeks.org/string-class-in-java/)。

1)计算前导零。
2)使用 StringBuffer 替换功能删除等于以上计数的字符。

```java
// Java program to remove leading/preceding zeros
// from a given string
import java.util.Arrays;
import java.util.List;

/* Name of the class to remove leading/preceding zeros */
class RemoveZero
{
    public static String removeZero(String str)
    {
        // Count leading zeros
        int i = 0;
        while (i < str.length() && str.charAt(i) == '0')
            i++;

        // Convert str into StringBuffer as Strings
        // are immutable.
        StringBuffer sb = new StringBuffer(str);

        // The  StringBuffer replace function removes
        // i characters from given index (0 here)
        sb.replace(0, i, "");

        return sb.toString();  // return in String
    }

    // Driver code
    public static void main (String[] args)
    {
        String str = "00000123569";
        str = removeZero(str);
        System.out.println(str);
    }
}
```

输出:

```java
123569

```

[在 C++中删除字符串的前导零](https://www.geeksforgeeks.org/remove-trailing-zeros-string-c/)

本文由 Somesh Awasthi 先生供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 什么时候在 StringBuilder 上使用 StringJoiner？

> 哎哎哎:# t0]https://www . geeksforgeeks . org/use-string joiner-string builder/

先决条件:[字符串连接器](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/)
字符串连接器非常有用，当你需要在一个流中连接字符串时。
**任务:**假设我们想要字符串“[乔治:莎莉:弗雷德]”，其中我们给出了一个包含“乔治”、“莎莉”和“弗雷德”的字符串数组。
StringJoiner 提供 *add(String str)* 方法来基于构造函数中提供的分隔符、前缀和后缀来连接字符串，但是如果我们使用 [StringBuilder](https://www.geeksforgeeks.org/g-fact-27-string-vs-stringbuilder-vs-stringbuffer/) 来执行我们的任务，那么首先我们必须追加前缀，然后遍历字符串数组，并在每个元素后追加所需的分隔符，最后追加前缀。下面是演示这两种方法的 java 程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate use of
// StringJoiner class over StringBuilder class

import java.util.StringJoiner;

public class Test
{
    public static void main(String[] args)
    {
        // given string array
        String str[] = {"George","Sally","Fred"};

        // By using StringJoiner class

        // initializing StringJoiner instance with
        // required delimiter, prefix and suffix
        StringJoiner sj = new StringJoiner(":", "[", "]");

        // concatenating strings
        sj.add("George").add("Sally").add("Fred");

        // converting StringJoiner to String
        String desiredString = sj.toString();

        System.out.println(desiredString);

        // By using StringBuilder class

        // declaring empty stringbuilder
        StringBuilder sb = new StringBuilder();

        // appending prefix
        sb.append("[");

        // checking for empty string array
        if(str.length>0)
        {
            // appending first element
            sb.append(str[0]);

            // iterating through string array
            // and appending required delimiter
            for (int i = 1; i < str.length; i++)
            {
                sb.append(":").append(str[i]);
            }
        }

        // finally appending suffix
        sb.append("]");

        // converting StringBuilder to String
        String desiredString1 = sb.toString();

        System.out.println(desiredString1);
    }
}
```

输出:

```java
[George:Sally:Fred]
[George:Sally:Fred]
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
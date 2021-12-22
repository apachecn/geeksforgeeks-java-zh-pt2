# 在 Java 中修剪(去掉前导和尾随空格)一个字符串

> 原文:[https://www . geesforgeks . org/trim-remove-前导-尾随-空格-字符串-java/](https://www.geeksforgeeks.org/trim-remove-leading-trailing-spaces-string-java/)

给定一个字符串，从该字符串中移除所有前导和尾随空格并返回它。

示例:

```
Input :  str = "   Hello World   "
Output : str = "Hello World"

Input :  str = "      Hey  there    Joey!!!      "
Output : str = "Hey  there    Joey!!!"

```

*   我们可以借助 **trim()** 来消除 Java 中字符串的前导空格和尾随空格。
*   trim()方法在 java.lang 包的 String 类下定义。
*   它没有消除字符串的中间空格。
*   通过调用 trim()方法，返回一个新的 String 对象。
*   它不会替换字符串对象的值。因此，如果我们想要访问新的字符串对象，我们只需要将其重新分配给旧的字符串，或者将其分配给新的变量。

**它是如何工作的？**
对于空格字符，unicode 值为“\u0020”。此方法检查字符串前后的 unicode 值，如果存在，则消除空格(前导和尾随)并返回字符串(不带前导和尾随空格)。

```
public class remove_spaces
{
    public static void main(String args[])
    {
        String str1 = "  Hello World  ";
        System.out.println(str1);
        System.out.println(str1.trim());

        String str2 = "      Hey  there    Joey!!!      ";
        System.out.println(str2);
        System.out.println(str2.trim());
    }
}
```

输出:

```
  Hello World  
Hello World
      Hey  there    Joey!!!  
Hey  there    Joey!!!    

```

本文由 **[基什莱·维尔马](https://www.linkedin.com/in/kishlayverma/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
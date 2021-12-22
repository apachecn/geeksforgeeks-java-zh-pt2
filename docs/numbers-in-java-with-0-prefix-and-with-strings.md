# Java 中的数字(带 0 前缀和字符串)

> 原文:[https://www . geesforgeks . org/numbers-in-Java-with-0-prefix-and-with-strings/](https://www.geeksforgeeks.org/numbers-in-java-with-0-prefix-and-with-strings/)

考虑下面的 Java 程序。

```
import java.io.*;
class GFG
{
    public static void main (String[] args)
    {
        int x = 012;
        System.out.print(x);
    }
}
```

输出:

```
10
```

上述输出的原因是，当前缀为 0 时，该值被认为是八进制的，因为八进制的 12 是十进制的 10，所以结果是 10。同样，如果 i = 0112，结果将是 74(十进制)。这个行为和 C/C++一样(见[这个](https://www.geeksforgeeks.org/output-of-c-program-set-27-2/))。

还有，

```
import java.io.*;
class GFG
{
    public static void main (String[] args)
    {
        String s = 3 + 2 + "hello" + 6 + 4;
        System.out.print(s);
    }
}
```

输出:

```
5hello64
```

Java 将引入字符串之前的数字作为 int，一旦引入字符串文字，以下所有数字都被视为字符串。

本文由 **Hiresh Trivedi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
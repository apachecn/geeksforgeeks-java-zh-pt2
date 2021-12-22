# 将 System.out.println()输出重定向到 Java 文件

> 原文:[https://www . geesforgeks . org/重定向-system-out-println-output-a-file-in-Java/](https://www.geeksforgeeks.org/redirecting-system-out-println-output-to-a-file-in-java/)

*System.out.println()* 主要用于向控制台打印消息。然而，我们很少有人真正了解它的工作机制。

*   *System* is a class defined in *java.lang* package.
*   Out is an instance of *printstream* , which is a public static member of class *system* .
*   Because all instances of the *printstream* class have a public method *println ()* , we can also call the same method on out. We can assume that *system output* represents the standard output stream.

与上述主题相关的一个有趣的事实是，**我们也可以使用 *System.out.println()* 将消息打印到其他来源(而不仅仅是控制台)**。但是在这样做之前，我们必须使用系统类的以下方法重新分配标准输出:

```
System.*setOut*(PrintStream p);
```

**打印流**可用于将字符输出到文本文件。下面的程序创建文件 A.txt，并使用 System.out.println(

```
// Java program to demonstrate redirection in System.out.println()
import java.io.*;

public class SystemFact
{
    public static void main(String arr[]) throws FileNotFoundException
    {
        // Creating a File object that represents the disk file.
        PrintStream o = new PrintStream(new File("A.txt"));

        // Store current System.out before assigning a new value
        PrintStream console = System.out;

        // Assign o to output stream
        System.setOut(o);
        System.out.println("This will be written to the text file");

        // Use stored value for output stream
        System.setOut(console);
        System.out.println("This will be written on the console!");
    }
}
```

)写入文件

以非常相似的方式，我们也可以使用 System.out.println()来写入套接字的输出流。

本文由**阿舒托什·库马尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
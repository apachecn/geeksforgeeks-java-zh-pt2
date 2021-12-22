# ProcessBuilder 用 Java 创建一个基本的在线判卷

> 原文:[https://www . geesforgeks . org/process builder-in-Java-to-create-a-basic-online-judge/](https://www.geeksforgeeks.org/processbuilder-in-java-to-create-a-basic-online-judge/)

我们已经讨论了[流程和运行时间](https://www.geeksforgeeks.org/calling-external-program-java-using-process-runtime/)来创建外部流程。在这篇文章中，讨论了服务于相同目的的 ProcessBuilder。

让我们理解一个应用程序，在那里我们需要获得源代码并找到语言。应用程序需要一个字符串(包含源代码)作为输入。应用程序需要找出编写源代码的语言。源代码将有一个相关的扩展。例如–

*   C 语言的代码会有”。c "扩展
*   C++中的代码会有”。cpp "扩展
*   Java 中的代码会有”。java "扩展
*   Python 中的代码将具有”。py "扩展名

使用输入文件的名称，可以找到需要使用的语言。

回想一下，用 java 编译代码是通过命令–
“javac Main . Java”
完成的，要执行它，我们使用–
“Java Main”

其他语言也有类似的命令。因此，我们需要一个单独的文本文件，包含我们的软件应该逐一执行的所有命令。

如果出现错误(运行时或编译器错误)，我们的应用程序应该将错误日志写在一个单独的文本文件中。无论源代码产生什么样的输出，我们的应用程序都应该将它写入另一个文本文件。

我们在“语言”包中使用“进程构建器”类来执行操作系统进程。

现在我们必须先创造一个过程-

```java
ProcessBuilder pb = new ProcessBuilder("cmd"); 
```

请注意，我们使用的是“cmd”，因此我们的命令可以在命令提示符下轻松执行。

假设我们的命令在“commands.txt”文件中，我们希望将输出存储在“output.txt”中，并将错误日志存储在“error.txt”中。我们应该把它们都告诉 ProcessBuilder 对象。“ProccessBuilder”类有方法–

*   公共进程生成器重定向输出(文件文件)
*   公共进程生成器重定向输出(文件文件)
*   public ProcessBuilder 重定向错误文件

一切都准备好了，我们只需要开始我们的进程。调用进程就像一个线程。我们使用- pb.start()
开始我们的过程。

下面是一个示例 java 代码来编译和运行另一个 java 代码-

```java
// Java program to demonstrate use of ProcessBuilder
// to compile and run external files.
import java.util.*;
import java.io.*;
class Main
{
    public static void main(String [] args) throws IOException
    {
        try {
            // create a process
            ProcessBuilder pb = new ProcessBuilder("cmd");

            // take all commands as input in a text file
            File commands = new File("E:\\test\\commands.txt");

            // File where error logs should be written
            File error = new File("E:\\test\\error.txt");

            // File where output should be written
            File output = new File("E:\\test\\output.txt");

            // redirect all the files
            pb.redirectInput(commands);
            pb.redirectOutput(output);
            pb.redirectError(error);

            // start the process
            pb.start();
        }
        catch(Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

要使代码正常工作，请执行以下步骤-

1.  在 E 目录中创建一个名为 Text 的文件夹。
2.  创建两个名为“error.txt”和“output.txt”的空文本文件。
3.  创建一个名为“commands.txt”的文本文件，它应该有–
    javac Demo.java
    Java Demo
4.  创建一个名为“Demo.java”的文件，其中源代码应该出现在“Demo”类中，而“main(String[] args)”函数应该出现在“Demo”类中。
5.  最后编译并执行上面写的代码。
6.  如果有任何错误，日志将出现在“error.txt”文件中，以免输出显示在“output.txt”中。

**警告:**

*   确保您希望编译和执行的代码不包含可能导致程序永远运行的无限循环之类的东西。您可以通过允许源代码运行一段固定的时间来处理这种情况。例如，如果代码运行时间超过 10 秒，抛出一个类似“超过时间限制”的错误。为此，您可以在“进程”类中使用“等待()”函数。
*   您必须检查代码编译是否正确，只有这样，您才应该尝试运行它，否则会显示错误日志文件。

**优势-**

*   你可以使用这种技术创建自己的在线法官。
*   它将帮助您将软件与操作系统直接链接起来。

**runtime . getruntime . exec()和 ProcessBuilder 的区别:**
Runtime.getRuntime.exec()在单独的进程中执行指定的字符串命令。另一方面，ProcessBuilder 只接受一个字符串列表，其中数组或列表中的每个字符串都被认为是一个单独的参数。这些参数然后被连接成一个字符串，然后被传递给操作系统执行。

```java
   // ProcessBuilder takes a list of argyments
   ProcessBuilder pb =
   new ProcessBuilder("myCommand", "myArg1", "myArg2");

   // Runtime.getRuntime.exec() takes a single string
   Runtime.getRuntime.exec("myCommand myArg1 myArg2")

```

本文由**苏亚什·斯里瓦斯塔瓦**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
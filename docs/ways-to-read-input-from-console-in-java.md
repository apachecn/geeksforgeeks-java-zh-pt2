# 用 Java 读取控制台输入的方法

> 原文:[https://www . geesforgeks . org/Java 控制台输入读取方式/](https://www.geeksforgeeks.org/ways-to-read-input-from-console-in-java/)

在 Java 中，有四种不同的方法可以在命令行环境(控制台)中读取用户的输入。

**1。使用缓冲阅读器类**

这是 JDK1.0 中引入的获取输入的 Java 经典方法。该方法是通过将 System.in(标准输入流)包装在一个 InputStreamReader 中来使用的，该 InputStreamReader 包装在一个 BufferedReader 中，我们可以在命令行中读取用户的输入。

*   输入经过缓冲，以便有效读取。
*   包装代码很难记住。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate BufferedReader
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
public class Test {
    public static void main(String[] args)
        throws IOException
    {
        // Enter data using BufferReader
        BufferedReader reader = new BufferedReader(
            new InputStreamReader(System.in));

        // Reading data using readLine
        String name = reader.readLine();

        // Printing the read line
        System.out.println(name);
    }
}
```

**输入:**

```java
Geek
```

**输出:**

```java
Geek
```

**注:**

为了读取其他类型，我们使用了像 Integer.parseInt()、Double.parseDouble()这样的函数。要读取多个值，我们使用 split()。

**2。使用扫描仪类**

这可能是最优选的输入方法。Scanner 类的主要目的是使用正则表达式解析基元类型和字符串，但是，它也可以用于在命令行中读取用户的输入。

*   从标记化输入中解析原语(nextInt()、nextFloat()、…)的方便方法。
*   正则表达式可以用来查找标记。
*   读取方法不同步

要查看更多差异，请参见[这篇](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/)文章。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of Scanner in Java
import java.util.Scanner;

class GetInputFromUser {
    public static void main(String args[])
    {
        // Using Scanner for Getting Input from User
        Scanner in = new Scanner(System.in);

        String s = in.nextLine();
        System.out.println("You entered string " + s);

        int a = in.nextInt();
        System.out.println("You entered integer " + a);

        float b = in.nextFloat();
        System.out.println("You entered float " + b);

          // closing scanner
          in.close();
    }
}
```

**输入:**

```java
GeeksforGeeks
12
3.4
```

**输出:**

```java
You entered string GeeksforGeeks
You entered integer 12
You entered float 3.4
```

**3。使用控制台类**

它已经成为从命令行读取用户输入的首选方式。此外，它可以用于读取类似密码的输入，而不会呼应用户输入的字符；也可以使用格式字符串语法(如 System.out.printf())。

**优势:**

*   读取密码时不回显输入的字符。
*   读取方法是同步的。
*   可以使用格式字符串语法。
*   不适用于非交互环境(如集成开发环境)。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of System.console()
// Note that this program does not work on IDEs as
// System.console() may require console
public class Sample {
    public static void main(String[] args)
    {
        // Using Console to input data from user
        String name = System.console().readLine();

        System.out.println("You entered string " + name);
    }
}
```

**输入:**

```java
GeeksforGeeks
```

**输出:**

```java
You entered string GeeksforGeeks
```

**4。** [**使用命令行参数**](https://www.geeksforgeeks.org/command-line-arguments-in-java/)

竞争编码中最常用的用户输入。命令行参数以字符串格式存储。整数类的 parseInt 方法将字符串参数转换为整数。同样，对于 float 和其他在执行期间。args[]的用法就是在这种输入形式中出现的。信息的传递发生在程序运行期间。命令行给了参数[]。这些程序必须在 cmd 上运行。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to check for command line arguments
class Hello {
    public static void main(String[] args)
    {
        // check if length of args array is
        // greater than 0
        if (args.length > 0) {
            System.out.println(
                "The command line arguments are:");

            // iterating the args array and printing
            // the command line arguments
            for (String val : args)
                System.out.println(val);
        }
        else
            System.out.println("No command line "
                               + "arguments found.");
    }
}
```

**命令行参数:**

```java
javac GFG1.java
java Main Hello World
```

**输出:**

```java
The command line arguments are:
Hello
World
```

更多更快的读取输入方式，请参考[本](https://www.geeksforgeeks.org/fast-io-in-java-in-competitive-programming/)。

本文由 **D Raj Ranu** 供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
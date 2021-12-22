# Java 中的扫描仪类

> 原文:[https://www.geeksforgeeks.org/scanner-class-in-java/](https://www.geeksforgeeks.org/scanner-class-in-java/)

Scanner 是 java.util 包中的一个类，用于获取 int、double 等原语类型的输入。和琴弦。这是在 Java 程序中读取输入的最简单的方法，尽管如果您想要一种用于时间受限的场景的输入法，比如在竞争性编程中，效率不是很高。

*   To create an object of Scanner class, we usually pass the predefined object System.in, which represents the standard input stream. If we want to read input from a File, we can pass an object of file class.
*   To read the numeric value of a data type XYZ, the function to be used is nextXYZ (). For example, to read a value of type short, we can use nextShort ()
*   To read the string, we can use nextLine ().
*   To read a single character, we use next (). charAt(0)。 The next () function returns the next tag/word in the input as a string, and the charAt(0) function returns the first character in the string.

让我们看一下读取各种数据类型的代码片段。

```
// Java program to read data of various types using Scanner class.
import java.util.Scanner;
public class ScannerDemo1
{
    public static void main(String[] args)
    {
        // Declare the object and initialize with
        // predefined standard input object
        Scanner sc = new Scanner(System.in);

        // String input
        String name = sc.nextLine();

        // Character input
        char gender = sc.next().charAt(0);

        // Numerical data input
        // byte, short and float can be read
        // using similar-named functions.
        int age = sc.nextInt();
        long mobileNo = sc.nextLong();
        double cgpa = sc.nextDouble();

        // Print the values to check if the input was correctly obtained.
        System.out.println("Name: "+name);
        System.out.println("Gender: "+gender);
        System.out.println("Age: "+age);
        System.out.println("Mobile Number: "+mobileNo);
        System.out.println("CGPA: "+cgpa);
    }
}
```

输入:

```
Geek
F
40
9876543210
9.9

```

输出:

```
Name: Geek
Gender: F
Age: 40
Mobile Number: 9876543210
CGPA: 9.9
```

有时，我们必须检查我们读取的下一个值是否是某种类型的，或者输入是否已经结束(遇到了电渗流标记)。

然后，我们借助 hasNextXYZ()函数检查扫描仪的输入是否是我们想要的类型，其中 XYZ 是我们感兴趣的类型。如果扫描器有该类型的标记，函数返回 true，否则返回 false。例如，在下面的代码中，我们使用了 hasNextInt()。为了检查字符串，我们使用 hasNextLine()。同样，为了检查单个字符，我们使用 hasNext()。charAt(0)。

让我们看一下从控制台读取一些数字并打印它们的平均值的代码片段。

```
// Java program to read some values using Scanner
// class and print their mean.
import java.util.Scanner;

public class ScannerDemo2
{
    public static void main(String[] args)
    {
        // Declare an object and initialize with
        // predefined standard input object
        Scanner sc = new Scanner(System.in);

        // Initialize sum and count of input elements
        int sum = 0, count = 0;

        // Check if an int value is available
        while (sc.hasNextInt())
        {
            // Read an int value
            int num = sc.nextInt();
            sum += num;
            count++;
        }
        int mean = sum / count;
        System.out.println("Mean: " + mean);
    }
}
```

输入:

```
101
223
238
892
99
500
728

```

输出:

```
Mean: 397
```

本文由 **Sukrit Bhatnagar** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论
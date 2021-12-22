# 为什么需要关闭 Finally Block 中的 Java 流？

> 原文:[https://www . geeksforgeeks . org/为什么您需要关闭最终块中的 java 流/](https://www.geeksforgeeks.org/why-you-need-to-close-the-java-streams-in-finally-block/)

在 Java 中 **finally block** 是一个用于执行重要且常见代码的块。finally 块主要用于异常处理过程中，通过 try 和 catch 关闭流和文件。不管是否有异常，finally 块中的代码都会被执行。这确保了所有打开的文件都被正确关闭，并且所有正在运行的线程都被正确终止。因此，文件中的数据不会被破坏，并且用户是安全的。

最后，在 try 和 catch 块之后执行块。代码的流程是:

*   尝试
*   捕捉
*   最后

下面举两个例子说明异常是什么时候引起的，什么时候没有引起。

> 我们将观察到 finally 块在我们的两个代码中执行。

**例 1** : **代码**异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show the execution of the code
// when exception is caused

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {

            // open files
            System.out.println("Open files");

            // do some processing
            int a = 45;
            int b = 0;

            // dividing by 0 to get an exception
            int div = a / b;

            System.out.println("After dividing a and b ans is " + div);
        }

        catch (ArithmeticException ae) {
            System.out.println("exception caught");

            // display exception details
            System.out.println(ae);
        }

        finally {
            System.out.println("Inside finally block");

            // close the files irrespective of any exception
            System.out.println("Close files");
        }
    }
}
```

**Output**

```
Open files
exception caught
java.lang.ArithmeticException: / by zero
Inside finally block
Close files
```

**例 2** : **无一例外**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show the execution of the code
// when exception is not caused

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {

            // open files
            System.out.println("Open files");

            // do some processing
            int a = 45;
            int b = 5;

            int div = a / b;
            System.out.println("After dividing a and b ans is " + div);
        }

        catch (ArithmeticException ae) {

            System.out.println("exception caught");

            // display exception details
            System.out.println(ae);
        }

        finally {

            System.out.println("Inside finally block");

            // close the files irrespective of any exception
            System.out.println("Close files");
        }
    }
}
```

**Output**

```
Open files
After dividing a and b ans is 9
Inside finally block
Close files
```
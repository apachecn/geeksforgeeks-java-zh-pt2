# Java SE 7 中引入的异常处理版本增强功能

> 原文:[https://www . geesforgeks . org/version-enhancements-in-exception-handling-in-Java-se-7/](https://www.geeksforgeeks.org/version-enhancements-in-exception-handling-introduced-in-java-se-7/)

本文讨论了**1.7 版**中[甲骨文](https://www.geeksforgeeks.org/tag/oracle/)所做的增强及其实现。

作为 1.7 版本增强的一部分，在[异常处理](https://www.geeksforgeeks.org/exceptions-in-java/)中，Oracle 引入了以下两个概念:

1.  [用资源试试](https://www.geeksforgeeks.org/automatic-resource-management-java/)。
2.  [多个抓块](https://www.geeksforgeeks.org/multicatch-in-java/)。

<u>**[用资源试试](https://www.geeksforgeeks.org/automatic-resource-management-java/)**T5】</u>

在 1.6 版本之前，强烈建议编写 finally block 来关闭所有作为 [try block](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/) 的一部分打开的资源。

**例如:**

```
// Java program to illustrate cleaning of
// resources before Java 7

import java.io.*;
import java.util.*;

class Resource {
    public static void main(String args[])
    {
        BufferedReader br = null;
        String str = " ";

        System.out.println(
            "Enter the file path");
        br
            = new BufferedReader(
                new InputStreamReader(
                    System.in));

        try {

            str = br.readLine();

            String s;

            // file resource
            br
                = new BufferedReader(
                    new FileReader(str));

            while ((s = br.readLine()) != null) {
                // print all the lines
                // in the text file
                System.out.println(s);
            }
        }
        catch (IOException e) {
            e.printStackTrace();
        }

        // This part was compulsory before Java 7
        // but with the introduction of
        // try with resource in Java 7
        // this part is optional now.
        finally {
            try {
                if (br != null)

                    // closing the resource
                    // in 'finally' block
                    br.close();
            }
            catch (IOException ex) {
                ex.printStackTrace();
            }
        }
    }
}
```

**输出:**

```
hello
java

```

**资源试用优势:**

1.  **试配资源**的主要优势在于，作为[试配块](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/)的一部分打开的资源，一旦控制正常或异常到达试配块的末尾，就会被**自动关闭**。因此，我们不需要显式关闭它。因此，编程的复杂性将会降低。
2.  我们可以声明任意数量的资源，但是所有这些资源都应该用分号(；)

    ```
    try(R1;R2;R3)
    {
    - - - - - - -
    - - - - - - -
    }

    ```

3.  所有的资源都应该是[可自动锁定的](https://www.geeksforgeeks.org/automatic-resource-management-java/)资源。当且仅当相应的类
    直接或间接地实现了 java.lang.AutoCloseable 接口时，资源被称为是可自动关闭的。
    比如所有数据库相关、网络相关、文件 IO 相关的资源都已经实现了 AutoCloseable 接口。
4.  所有资源引用变量都是隐式最终的，因此我们不能在 try 块中执行重新分配。例如，在下面的代码中，我们正在重新分配 **br** 的值，我们得到了一个[编译时错误](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/)。

    ```
    try (BufferedReader br = new BufferedReader(new FileReader("abc.txt"))) {
        br = new BufferedReader(new FileReader("abc.txt"));
    }
    ```

5.  在 1.6 版本之前，try 后面应该跟有 [catch](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/) 或者 final，但是 1.7 版本我们只能用没有 catch 或者 final 语句的资源进行 try。

    ```
    try(R)
    {  //valid
    }

    ```

下面是增强的 try-catch 块的实现:

```
// Try opening a file
try (bufferedReader br = new BufferedReader(new FileReader("abc.txt"))) {
}

// Catch an exception
catch (IOException e) { // handling code }

// After the execution of try and catch is completed
// the file is closed automatically by Java
```

<u>**[多抓块](https://www.geeksforgeeks.org/multicatch-in-java/):**T5】</u>

直到 1.6 版本，如果我们希望为同一个 try 块处理多个异常，我们必须在多个 catch 语句中定义所有异常。

**例如:**

```
// For this try block
try {
    -------- - -------- -
}

// Catching Arithmetic Exception
catch (ArithmeticException e) {
    e.printStackTrace();
}

// Catching Nullpointer Exception
catch (e) {
    e.printStackTrace();
}

// Catching Class Cast Exception
catch (ClassCastException e) {
    System.out.println(e.getMessage());
}

// Catching IOException
catch (IOException e) {
    System.out.println(e.getMessage());
}
```

为了克服这个问题，在 1.7 版本中引入了“多捕捉块”的概念。因此，所有的异常都可以用**单个 catch 语句**来处理。

下面是多重捕获语句的实现:

```
try {
    ------ - ------ -
}
catch (ArithmeticException | NullpointerException
       | ClassCastException | IOException e) {
    System.out.println(e.getMessage());
}
```

**注意:**在多 catch 块中，异常类型之间不应该有任何关系(子对父或者父对子或者同一个类型)。
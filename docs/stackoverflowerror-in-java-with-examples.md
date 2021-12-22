# Java 中的 StackOverflowError 示例

> 原文:[https://www . geeksforgeeks . org/stackoverflow error-in-Java-with-examples/](https://www.geeksforgeeks.org/stackoverflowerror-in-java-with-examples/)

**StackOverflowError** 是一个 Java 不允许捕捉的错误，例如，堆栈空间不足，因为这是最常见的[运行时错误](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/)之一。

StackOverflowError 的主要原因是我们**没有给我们的[递归函数](https://www.geeksforgeeks.org/recursive-functions/)或者模板提供合适的终止条件**，这意味着它会变成一个[无限循环](https://www.geeksforgeeks.org/infinite-loop-puzzles-java/)。

【StackOverflowError 什么时候遇到的？

当我们调用一个方法时，一个新的[堆栈](https://www.geeksforgeeks.org/java-virtual-machine-jvm-stack-area/)框架将在调用堆栈或线程堆栈大小上创建。这个堆栈框架保存被调用方法的参数，主要是局部变量和方法的返回地址。这些堆栈框架的创建将是迭代的，并且只有在嵌套方法中找到方法调用的结尾时才会停止。在这个过程中，如果 [JVM](https://www.geeksforgeeks.org/java-virtual-machine-jvm-stack-area/) 为需要创建的新堆栈帧耗尽空间，它将抛出一个堆栈溢出错误。

**例如:**缺少合适的终止条件或没有终止条件。这是这种被称为无终止或无限递归的情况的主要原因。

**下面给出的是无限递归的实现:**

```
// Java program to demonstrate
// infinite recursion error

public class StackOverflowErrorClass {
    static int i = 0;

    // Method to print numbers
    public static int printNumber(int x)
    {

        i = i + 2;
        System.out.println(i);
        return i + printNumber(i + 2);
    }

    public static void main(String[] args)
    {
        // Recursive call without any
        // terminating condition
        StackOverflowErrorClass.printNumber(i);
    }
}
```

**运行时错误:**

> java 代码中的运行时错误:-在 Java . io . printstream . write(printstream . Java:526)处的线程“main”Java . lang . stackoverflow Error
> 中出现异常，在 Java . io . printstream . printstream(printstream . Java:597)处的线程
> 在 Java . io . printstream . println(printstream . Java:736)处的线程
> 在 stackoverflow errorrclass . printsnumber(stackoverflow errorrclas . Java:13)处的线程
> 中出现异常
> 。
> 。

***注意:**请在你的系统上运行这个来查看抛出的错误，由于堆栈大小的原因，这个可能不会在联机 IDE 上显示错误。*

**如何修复 StackOverflowError？**

1.  **Avoiding repetitive calls:** Try to introduce a proper terminating condition or some condition for the recursive calls to ensure that it terminates.

    **下面给出了适当终止条件的实现:**

    ```
    // Java Program to demonstrate proper
    // use of terminating condition

    // Printing natural numbers
    public class stackOverflow {
        static int i = 0;
        public static int printNumber(int x)
        {

            i = i + 2;
            System.out.println(i);

            // Terminating condition
            if (i == 10)
                return i;

            return i + printNumber(i + 2);
        }

        public static void main(String[] args)
        {
            stackOverflow.printNumber(i);
        }
    }
    ```

    **Output:**

    ```
    2
    4
    6
    8
    10

    ```

2.  **Increasing the Stack Size:** The second method could be, if you notice that it’s implemented correctly still we see an error, then we can avoid that only by increasing the Stack Size in order to store the required number of recursive calls. This is achieved by changing the settings of the compiler.

    **类之间的循环关系**是两个不同的类在它们的构造函数中相互实例化时产生的关系。

    之所以会遇到 StackOverflowError，是因为类 A1 的构造函数正在实例化类 A2，而类 A2 的构造函数又在实例化类 A1，并且反复出现，直到我们看到 StackOverflow。这个错误主要是由于构造函数调用不好，也就是互相调用，这甚至不是必需的，也没有任何意义，所以我们可以避免在代码中引入它们。

    **下面给出的是类间循环关系的实现:**

    ```
    // Java Program to demonstrate
    // cyclic relationship between class

    public class A1 {
        public A2 type2;
        public A1()
        {

            // Constructor of A2 is called
            // hence object of A2 is created
            type2 = new A2();
        }

        public static void main(String[] args)
        {

            // Cycle is started by
            // invoking constructor of class A1
            A1 type1 = new A1();
        }
    }

    class A2 {
        public A1 type1;
        public A2()
        {

            // Constructor of A1 is called
            // hence object of A1 is created
            type1 = new A1();
        }
    }
    ```

    **运行时错误:**

    > java 代码中的 RunTime 错误:-线程“main”中的异常 Java . lang . stackoverflow Error
    > 位于 A2。<init>(A1.java:32)
    > 在 A1。<init>(A1.java:13)
    > 在 A2。<init>(A1.java:32)
    > 。
    > 。
    > 。</init></init></init>

    ***注意:**这个会一直重复，无限递归被这些无限循环调用看到。*
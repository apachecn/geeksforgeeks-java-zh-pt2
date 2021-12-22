# 理解 Java 中的公共静态 void main(String[]args)

> 原文:[https://www . geesforgeks . org/understanding-public-static-void-mainstring-args-in-Java/](https://www.geeksforgeeks.org/understanding-public-static-void-mainstring-args-in-java/)

在 Java 程序中，程序开始执行的点或者简单地说 Java 程序的入口点是 **main()** 方法。因此，它是 Java 最重要的方法之一，正确理解它非常重要。

**main()方法最常见的语法:**

```
class GeeksforGeeks {
    public static void main(String[] args)
    {
        System.out.println("I am a Geek");
    }
}
```

```
I am a Geek
```

**解释:**
公共静态虚空主语句中的每一个字都对 JVM 有了意义。

1.  **公共:**是一个*访问修饰符*，指定从哪里以及谁可以访问该方法。将 *main()* 方法公之于众，可以在全球范围内使用。它是公开的，这样 JVM 就可以从类外部调用它，因为它不在当前类中。

    ```
    class GeeksforGeeks {
        private static void main(String[] args)
        {
            System.out.println("I am a Geek");
        }
    }
    ```

    ```
    Error: Main method not found in class, please define the main method as:
    public static void main(String[] args)
    or a JavaFX application class must extend javafx.application.Application
    ```

2.  **静态:**是一个*关键字*，当与一个方法关联时，使其成为一个类相关的方法。 *main()* 方法是静态的，这样 JVM 就可以在不实例化类的情况下调用它。这也节省了不必要的内存浪费，而这些内存本来是由只声明用于 JVM 调用 *main()* 方法的对象使用的。

    ```
    class GeeksforGeeks {
        public void main(String[] args)
        {
            System.out.println("I am a Geek");
        }
    }
    ```

    ```
    Error: Main method is not static in class test, please define the main method as:
    public static void main(String[] args)
    ```

3.  **Void:** 是一个关键字，用来指定一个方法不返回任何东西。由于*主()*法不返回任何东西，其返回类型为*虚空*。一旦 *main()* 方法终止，java 程序也会终止。因此，从 *main()* 方法返回没有任何意义，因为 JVM 不能用它的返回值做任何事情。

    ```
    class GeeksforGeeks {
        public static int main(String[] args)
        {
            System.out.println("I am a Geek");
            return 1;
        }
    }
    ```

    ```
    Error: Main method not found in class, please define the main method as:
    public static void main(String[] args)
    or a JavaFX application class must extend javafx.application.Application
    ```

4.  **main:** 是 Java main 方法的名字。它是 JVM 寻找的作为 java 程序起点的标识符。不是关键词。

    ```
    class GeeksforGeeks {
        public static void myMain(String[] args)
        {
            System.out.println("I am a Geek");
        }
    }
    ```

    ```
    Error: Main method not found in class, please define the main method as:
    public static void main(String[] args)
    or a JavaFX application class must extend javafx.application.Application
    ```

5.  **String[] args:** It stores Java *command line arguments* and is an array of type *java.lang.String* class. Here, the name of the String array is *args* but it is not fixed and user can use any name in place of it.

    ```
    class GeeksforGeeks {
        // javac GeeksforGeeks.java
        // java GeeksforGeeks 1 2 3
        public static void main(String[] args)
        {
            for (String elem : args)
                System.out.println(elem);
        }
    }
    ```

    ```
    1
    2
    3
    ```

    除了上面提到的 main 的签名，您可以使用**公共静态 void main(String args[])** 或**公共静态 void main(String… args)** 在 java 中调用 main 函数。如果它的形式参数与字符串数组的形式参数匹配，则调用主方法。

    **主方法可以是 int 吗？如果没有，为什么？**

    ```
    class GeeksforGeeks {

        public static int main(String[] args) {

            System.out.println("GeeksforGeeks");
        }
    }
    ```

    即使我们将 main 的返回类型声明为 int，Java 也不会隐式返回 int。
    我们会得到编译时错误

    > prg1.java:6:错误:缺少返回语句
    > }
    > ^
    > 1 错误

    ```
    class GeeksforGeeks {

        public static int main(String[] args) {

            System.out.println("GeeksforGeeks");
            return 0;
        }
    }
    ```

    现在，即使我们自己显式地从 int main 返回 0 或整数。
    我们得到运行时错误。

    > 错误:main 方法必须返回类 GeeksforGeeks 中 void 类型的值，请
    > 将 Main 方法定义为:
    > 公共静态 void main(String[] args)

    **解释–**
    **从 main 返回 int 的 C 和 C++程序**是操作系统的**进程**。C 和 C++中 main 返回的 **int 值**为**退出代码或退出状态**。C 或 C++程序的退出代码说明了程序终止的原因。退出代码 0 表示成功终止。但是，非零退出状态表示错误。例如，退出代码 1 描述了各种错误，如“被零除”

    任何子进程的父进程都在等待子进程的退出状态。并且在接收到子进程的退出状态后，从进程表中清除子进程，并释放分配给它的资源。这就是为什么 C 和 C++程序(操作系统的程序)必须显式或隐式地从 main 传递退出状态。

    然而，java 程序在 JVM 中作为**“主线程”**运行。Java 程序甚至不是操作系统的直接进程。Java 程序和操作系统之间没有直接的交互。没有直接将资源分配给 Java 程序，或者 Java 程序没有在进程表中占据任何位置。那么，它应该将退出状态返回给谁呢？这就是为什么 Java 的 main 方法被设计成不返回 int 或 exit 状态。

    但是 JVM 是一个操作系统的进程，JVM 可以以一定的退出状态终止。**借助 java.lang.Runtime.exit(int 状态)**或 **System.exit(int 状态)**
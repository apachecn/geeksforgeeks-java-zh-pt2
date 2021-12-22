# 在 Java 中使用预定义的类名作为类名或变量名

> 原文:[https://www . geesforgeks . org/using-predefined-class-name-class-variable-name-Java/](https://www.geeksforgeeks.org/using-predefined-class-name-class-variable-name-java/)

在 Java 中，允许使用预定义的类名作为类名或变量名。但是根据 [Java 规范语言(3.9)](http://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#jls-3.9)Java 中命名的基本规则是不能使用关键字作为类名、变量名或者用于包的文件夹名。
在 Java 中使用任何预定义类都不会导致这样的编译器错误，因为 Java 预定义类不是关键字。

**以下是 Java 中一些无效的变量声明:**

```
boolean break = false; // not allowed as break is keyword
int boolean = 8; // not allowed as boolean is keyword
boolean goto = false; // not allowed as goto is keyword
String final = "hi"; // not allowed as final is keyword
```

**使用预定义的类名作为用户定义的类名**

1.  **问题:**我们可以将类名作为程序中预定义的类名之一吗？
    **回答:**是的，我们可以拥有它。以下是使用**编号**作为用户定义类别的示例

```
// Number is predefined class name in java.lang package
// Note : java.lang package is included in every java program by default
public class Number
{
    public static void main (String[] args)
    {
        System.out.println("It works");
    }
}
```

输出:

```
It works

```

*   **Using String as User Defined Class:**

    ```
    // String is predefined class name in java.lang package
    // Note : java.lang package is included in every java program by default
    public class String
    {
        public static void main (String[] args)
        {
            System.out.println("I got confused");
        }
    }
    ```

    但是，在这种情况下，您会得到如下运行时错误:

    ```
    Error: Main method not found in class String, please define 
    the main method as:
       public static void main(String[] args)

    ```

    **解释:**这是因为[主线程](https://www.geeksforgeeks.org/main-thread-java/)正在用预定义的**字符串类**数组参数寻找*主*方法()。但是在这里，它得到了带有用户定义的 String 类的 *main* 方法()。每当主线程看到一个类名时，它就试图逐个范围地搜索该类。首先它会出现在你的程序中，然后出现在你的包中。如果没有找到，那么 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 遵循委托层次原则加载该类。因此你会得到运行时错误。
    要运行上面的程序，我们还可以提供 String 类的完整路径，即 *java.lang.String* 。

    ```
    // String is predefined class name in java.lang package
    // Note : java.lang package is included in every java program by default
    public class String
    {
        public static void main (java.lang.String[] args)
        {
            System.out.println("I got confused");
        }
    }
    ```

    输出:

    ```
    I got confused

    ```

    **使用预定义的类名作为用户定义的变量名**

    **问题:**我们可以在程序中有一个变量名作为预定义的类名之一吗？
    **回答:**是的，我们可以拥有它。

    ```
    // Number is predefined class name in java.lang package
    // Note : java.lang package is included in every java program by default
    public class Number
    {
        // instance variable
        int Number = 20;

        public static void main (String[] args)
        {
            // reference variable
            Number Number = new Number();

            // printing reference
            System.out.println(Number);

            // printing instance variable
            System.out.println(Number.Number);
        }
    }
    ```

    输出:

    ```
    Number@15db9742
    20

    ```

    本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
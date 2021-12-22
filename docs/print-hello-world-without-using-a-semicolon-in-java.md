# 在 Java 中不使用分号打印 Hello World】

> 原文:[https://www . geesforgeks . org/print-hello-world-不使用分号的 java/](https://www.geeksforgeeks.org/print-hello-world-without-using-a-semicolon-in-java/)

按照基本原则， [Java](https://www.geeksforgeeks.org/java/) 中的每个语句都必须以分号结束。然而，与其他语言不同，Java 中几乎所有的语句都可以被视为表达式。然而，有一些情况下，我们可以编写一个没有分号的运行程序。如果我们将语句放在一个带有一对空白括号的 if/for 语句中，我们就不必用分号来结束它。此外，调用返回 void 的函数在这里不起作用，因为 void 函数不是表达式。

**方法:**

1.  Use the if-else statement
2.  僧曰附录()你好吗 StringBuilder(字符串生成器)1860 年
3.  String class using the equals method

**方法一:** [使用 if 语句](https://www.geeksforgeeks.org/java-if-statement-with-examples/)

## Java

```
// Java program to Print Hello World Without Semicolon
// Using if statement

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Using if statement to
        // print hello world
        if (System.out.printf("Hello World") == null) {
        }
    }
}
```

**输出**

```
Hello World
```
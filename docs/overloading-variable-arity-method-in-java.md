# Java 中重载变量 Arity 方法

> 原文:[https://www . geesforgeks . org/overload-variable-arity-method-in-Java/](https://www.geeksforgeeks.org/overloading-variable-arity-method-in-java/)

这里我们将讨论 varargs/variary 方法以及如何重载这种类型的方法。因此，让我们首先了解什么是变量 arity 方法及其语法。变量 arity 方法也称为 varargs 方法，可以接受指定类型的多个变量。

> **注意:**直到 1.4 版本都没有 varargs 方法。它是在 1.5 版本中引入的，并且一直存在。

**语法:**

```java
methodName(dataType...variableName)
```

**“…”**表示该方法可以接受任意数量的指定数据类型的参数，甚至为零。内部 varargs 方法是使用一维(1D)数组概念实现的。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Variable arity Method

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // Main driver method
    public static void main(String[] args)
    {
        // Calling varargs sum method with no parameter
        sum();

        // Calling varargs sum method with two int type
        // parameters
        sum(10, 10);

        // Calling varargs sum method with three int type
        // parameters
        sum(15, 15, 20);
    }

    // Method 2
    // varargs method expects zero or
    // more int type parameters
    public static void sum(int... x)
    {
        int total = 0;

        // Takes parameters passed to sum, one at a time
        // later summing it up
        for (int y : x) {
            total += y;
        }

        // Print the sum on console
        System.out.println("Sum : " + total);
    }
}
```

**Output**

```java
Sum : 0
Sum : 20
Sum : 50
```

现在让我们来看看一些关于 varargs 方法和参数的可接受顺序的重要事实。以下几点将有助于提高对 varargs 方法的理解，具体如下:

**1.1** Varargs 参数可以和正常参数混合使用。

```java
methodName(int x, String...y)
```

<figure class="table">

| 方法名称（10） | 有效的 |
| 方法名(10，“你好”) | 有效的 |

</figure>

**1.2** 在混合过程中，varargs 参数应该是最后一个

<figure class="table">

| 方法名(int x，String…y) | effective |
| 方法名(int…x，String y) | be invalid |

</figure>

**1.3** 只能有一个 vararg 参数

<figure class="table">

| 方法名(int x，int y，String…z) | effective |
| 方法名(int…x，String…y) | be invalid |

</figure>

**1.4** 一般情况下，varargs 方法会获得最后一个优先级意味着如果没有其他方法**匹配**，那么只会调用 varargs 方法。下面的例子将会跨越这个概念。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        sum(9);
        // Since we are passing two int type arguments and
        // we have defined a function which expects two int
        // type parameters so that particular method (normal
        // sum method ) will be called and not varargs
        // method.
        sum(10, 20);
    }

    // normal maethod which expects two int type parameters
    public static void sum(int x, int y)
    {
        System.out.println("normal method");
        System.out.println("Sum : " + (x + y));
    }

    // varargs method which expects zero or more int type
    // parameters
    public static void sum(int... x)
    {
        System.out.println("varargs method");
        int total = 0;
        for (int y : x) {
            total += y;
        }
        System.out.println("Sum : " + total);
    }
}
```

**Output**

```java
varargs method
Sum : 9
normal method
Sum : 30
```

**1.5** 使用数组传递变量个数的参数是 varargs 的老方法，不适合。

让我们来讨论重载 varargs 方法。我们知道，如果一个类有多个同名但不同参数的方法，这就是所谓的方法重载。这同样适用于 varargs 方法。让我们也这样做

**实现:**这里的“vaTest”是重载的，因为 vaTest 的每次出现都需要不同的参数列表。将调用 vaTest 的哪个事件来执行对参数的操作取决于每个参数的类型。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Overloading in Variable
// arity

// Importing input output classes
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        vaTest(1, 2, 3, 4, 5);
        vaTest(true, true, false, true);
        vaTest("Message", 10, 20);
    }

    // Method 1
    // varargs method which expects zero or
    // more int type parameters
    public static void vaTest(int... x)
    {

        // Print statement on console
        System.out.println(
            "varargs method with int type arguments");

        for (int y : x) {
            System.out.print(" " + y);
        }
        System.out.println();
    }

    // Method 3
    // varargs method which expects zero or
    // more boolean type parameters
    public static void vaTest(boolean... x)
    {

        // Print statement on console
        System.out.println(
            "varargs method with boolean type arguments");

        for (boolean y : x) {
            System.out.print(" " + y);
        }
        System.out.println();
    }

    // Method 3
    // varargs() method which expects first parameter to be
    // of String type and then zero or more int type
    // parameters.
    public static void vaTest(String msg, int... x)
    {

        // Print statement on console
        System.out.print(msg);

        for (int y : x) {
            System.out.print(" " + y);
        }

        // New line
        System.out.println();
    }
}
```

**Output**

```java
varargs method with int type arguments
 1 2 3 4 5
varargs method with boolean type arguments
 true true false true
Message 10 20
```

> **注意:**一个 vararg 方法也可以被非 varargs 方法重载。vaTest(布尔 x)对重载 vaTest 有效。只有在传递了一个布尔参数的情况下才会调用这个 vaTest(布尔 x)，否则(布尔…x)。

> **歧义:**还会出现如下所列的一些歧义:
> 
> *   对 vaTest 的调用是不明确的，因为 varargs 可以是空的，因此这个调用可以等价地转换为 vaTest(int…x)或 vaTest(int…y)。
> *   假设我们有两种方法，vaTest(int…x)和 vaTest(int a，int…x)。现在，如果我们调用 vaTest(1)，这两种格式都有效。因此模糊性，
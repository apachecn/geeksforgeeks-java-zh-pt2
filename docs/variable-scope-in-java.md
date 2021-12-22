# Java 中变量的范围

> 原文:[https://www.geeksforgeeks.org/variable-scope-in-java/](https://www.geeksforgeeks.org/variable-scope-in-java/)

变量的作用域是程序中可访问变量的部分。像 C/C++一样，在 Java 中，所有标识符都是词汇(或静态)范围的，即变量的范围可以在编译时确定，并且独立于函数调用堆栈。
Java 程序是以类的形式组织的。每个类都是某个包的一部分。Java 范围规则可以分为以下几类。

**成员变量(类级别范围)**

这些变量必须在类内部(任何函数外部)声明。它们可以在课堂上的任何地方直接访问。让我们看一个例子:

```
public class Test
{
    // All variables defined directly inside a class 
    // are member variables
    int a;
    private String b;
    void method1() {....}
    int method2() {....}
    char c;
}
```

*   我们可以在类中的任何地方声明类变量，但是不能在方法之外。
*   成员变量的指定访问不影响它们在类中的作用域。
*   可以使用以下规则在类外部访问成员变量

```
Modifier      Package  Subclass  World

public          Yes      Yes     Yes

protected       Yes      Yes     No

Default (no
modifier)       Yes       No     No

private         No        No     No
```

**局部变量(方法级范围)**

方法内部声明的变量具有方法级别的作用域，不能在方法外部访问。

```
public class Test
{
    void method1() 
    {
       // Local variable (Method level scope)
       int x;
    }
}
```

**注意:**方法执行结束后局部变量不存在。

这是方法作用域的另一个例子，只是这次变量作为参数传入了方法:

```
class Test
{
    private int x;
    public void setX(int x)
    {
        this.x = x;
    }
}
```

上面的代码使用[这个关键字](https://www.geeksforgeeks.org/this-reference-in-java/)来区分局部变量和类变量。

作为练习，预测以下 Java 程序的输出。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Test
{
    static int x = 11;
    private int y = 33;
    public void method1(int x)
    {
        Test t = new Test();
        this.x = 22;
        y = 44;

        System.out.println("Test.x: " + Test.x);
        System.out.println("t.x: " + t.x);
        System.out.println("t.y: " + t.y);
        System.out.println("y: " + y);
    }

    public static void main(String args[])
    {
        Test t = new Test();
        t.method1(5);
    }
}
```

**输出:**

```
Test.x: 22
t.x: 22
t.y: 33
y: 44
```

**循环变量(块范围)**
方法中一对括号“{”和“}”内声明的变量只有括号内的范围。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Test
{
    public static void main(String args[])
    {
        {
            // The variable x has scope within
            // brackets
            int x = 10;
            System.out.println(x);
        }

        // Uncommenting below line would produce
        // error since variable x is out of scope.

        // System.out.println(x);
    }
}
```

**输出:**

```
10
```

作为另一个例子，请考虑使用 for 循环执行以下程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String args[])
    {
        for (int x = 0; x < 4; x++)
        {
            System.out.println(x);
        }

        // Will produce error
        System.out.println(x);
    }
}
```

**输出:**

```
11: error: cannot find symbol
        System.out.println(x);      
```

正确的方法是，

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Above program after correcting the error
class Test
{
    public static void main(String args[])
    {
        int x;
        for (x = 0; x < 4; x++)
        {
            System.out.println(x);
        }

       System.out.println(x);
    }
}
```

**输出:**

```
0
1
2
3
4
```

让我们看看循环范围的一个棘手的例子。预测后续程序的输出。如果你是普通的 C/C++程序员，你可能会感到惊讶。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String args[])
    {
        int a = 5;
        for (int a = 0; a < 5; a++)
        {
            System.out.println(a);
        }
    }
}
```

**输出:**

```
6: error: variable a is already defined in method go(int)
       for (int a = 0; a < 5; a++)       
                ^
1 error
```

注意:-在 C++中，它将运行。但是在 java 中这是一个错误，因为在 java 中，内循环和外循环的变量名称必须不同。
c++中一个类似的程序工作。参见[本](https://ide.geeksforgeeks.org/hWKCdM)。

作为练习，预测以下 Java 程序的输出。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String args[])
    {
        {
            int x = 5;
            {
                int x = 10;
                System.out.println(x);
            }
        }
    }
}
```

问:根据上面的知识，判断下面的代码是否会运行。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test {
    public static void main(String args[])
    {
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
        int i = 20;
        System.out.println(i);
    }
}
```

**输出:**

```
1
2
3
4
5
6
7
8
9
10
20
```

是的，它会跑！
仔细看程序，内环会在外环变量声明之前终止。所以先销毁内部循环变量，然后创建同名的新变量。

**Java 中关于变量作用域的一些要点:**

*   一般来说，一组花括号{ }定义了一个范围。
*   在 Java 中，我们通常可以访问一个变量，只要它是在与我们正在编写的代码相同的一组括号中定义的，或者是在定义该变量的花括号内的任何花括号中定义的。
*   在任何方法之外的类中定义的任何变量都可以被所有成员方法使用。
*   当一个方法具有与成员相同的局部变量时，“this”关键字可以用来引用当前的类变量。
*   对于要在循环结束后读取的变量，它必须在循环体之前声明。

本文由**里沙布·马赫塞**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
# Java 中 main()的有效变体

> 原文:[https://www.geeksforgeeks.org/valid-variants-main-java/](https://www.geeksforgeeks.org/valid-variants-main-java/)

我们知道，Java 代码从主方法开始执行。在运行时，如果 JVM 找不到任何主方法，那么我们会得到一个运行时异常:
**没有这样的方法错误** :

```
Main method not found in class, please define the main method as:
public static void main(String[] args) 
```

要避免这个问题，应该有主要的方法。我们还知道 java main 方法有一个特定的原型，看起来像:

> [**公静虚空主(String[] args)**](https://www.geeksforgeeks.org/understanding-public-static-void-mainstring-args-in-java/)

即使上面的语法(原型)很严格但有些小改动也是可以接受的。这使得它不是那么严格，如果我们执行任何更改，那么我们将得到一个运行时异常。我们可以对我们的主要方法做一些允许的修改。
以下变更可以接受。
让我们来了解 main()的不同有效变体。

*   **默认原型:**下面是用 Java 写 main()最常见的方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String[] args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

**主要语法的含义:**

```
public:  JVM can execute the method from anywhere.
static:  Main method can be called without object.
void:    The main method doesn't return anything.
main():  Name configured in the JVM.
String[]: Accepts the command line arguments.
args:- the name of the String array is args.

```

*   **修饰语的顺序:**我们可以在 main()中互换静态和公共的位置。

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java code to understand that The Order of Modifiers don't matters
class Test
{
    static public void main(String[] args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

*   **字符串数组参数的变体:**我们可以在字符串参数的不同位置放置方括号。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String[] args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String []args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String args[])
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

*   **Args 或任何东西:**我们可以写任何有效的 java 标识符，而不是 Args。你可以在这里写任何东西，你可以写你的名字或者公司的名字或者任何你想写的东西，但是它必须遵循作为 java 标识符的规则。
    T3】例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Gfg{

       public static void main(String[] geeksforgeeks){
               System.out.println("Instead of args we have written geeksforgeeks");
       }
}
```

**输出:**

```
Instead of args we have written geeksforgeeks
```

*   **var-args 代替 String 数组:**根据规则每当有一维数组的时候我们就可以用 Var-arg 参数代替数组。所以在这里，我们可以使用 var-args 更改字符串数组。(三点代替[])
    **例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java code-> using Var-Args instead of the array
//please note these code may not run in gfg IDE, better run it on other IDEs e.g, eclipse
class Gfg{

        final public static void main(String... args){
        System.out.println("Var-args main method");
    }
}
```

**输出:**

```
Var-args main method
```

*   **Final 修饰符 String 参数:**我们可以将 String args[]设为 Final。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(final String[] args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

*   **Final main 方法:**我们可以用 Final 关键字声明 main 方法。这不能改变执行或给出任何错误。
    **例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java code having the final main method
////please note these code may not run in gfg IDE, better run it on other IDEs e.g, eclipse
class Gfg{

    final public static void main(String[] args){

        System.out.println("final main method");

        }
}
```

**输出:**

```
final main method
```

*   **synchronized 关键字到静态 main 方法:**我们可以使 main()同步。

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java code having Synchronized main method
//please note these code may not run in gfg IDE, better run it on other IDEs e.g, eclipse
class Test
{
    public synchronized static void main(String[] args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

*   [**strictfp**](https://en.wikipedia.org/wiki/Strictfp) **关键字去静态主方法:** strictfp 可以用来限制浮点计算。

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java code-> using strictfp modifier in main method
//please note these code may not run in gfg IDE, better run it on other IDEs e.g, eclipse
class Test
{
    public strictfp static void main(String[] args)
    {
        System.out.println("Main Method");
    }
}
```

**输出:**

```
Main Method
```

*   **以上所有关键字的组合到静态主方法:**
    所以我们可以用以下修饰符来声明 java 主方法:
*   **重载 main 方法:**我们可以用不同类型的参数重载 Main()。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Test
{
    public static void main(String[] args)
    {
        System.out.println("Main Method String Array");
    }
    public static void main(int[] args)
    {
        System.out.println("Main Method int Array");
    }
}
```

**输出:**

```
Main Method String Array
```

*   **Main 方法的继承:** JVM 执行 Main()没有任何错误。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class A
{
    public static void main(String[] args)
    {
        System.out.println("Main Method Parent");
    }
}

class B extends A
{

}
```

两个类文件，a 类和 b 类是由编译器生成的。当我们处决其中任何一个的时候。类，JVM 执行时不会出错。

```
O/P: Java A
Main Method Parent
O/P: Java B
Main Method Parent
```

*   **方法隐藏 main()，但不覆盖:**由于 main()是静态的，派生类 main()隐藏基类 main。(详见[静态函数](https://www.geeksforgeeks.org/g-fact-63/)阴影。)

## Java 语言(一种计算机语言，尤用于创建网站)

```
class A
{
    public static void main(String[] args)
    {
        System.out.println("Main Method Parent");
    }
}
class B extends A
{
    public static void main(String[] args)
    {
        System.out.println("Main Method Child");
    }
}
```

两个类，a 类和 b 类是由 Java 编译器 javac 生成的。当我们执行。类，JVM 执行时不会出错。

```
O/P: Java A
Main Method Parent
O/P: Java B
Main Method Child
```

本文由**马赫什**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
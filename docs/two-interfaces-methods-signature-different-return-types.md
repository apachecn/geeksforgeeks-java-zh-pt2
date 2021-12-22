# 两个方法相同但签名相同但返回类型不同的接口

> 原文:[https://www . geesforgeks . org/two-interfaces-methods-signature-differential-return-type/](https://www.geeksforgeeks.org/two-interfaces-methods-signature-different-return-types/)

Java 不支持多重继承，但是我们可以使用接口达到多重继承的效果。在接口中，一个类可以实现多个接口，这是通过 extends 关键字无法实现的。
详见 java 中[多重继承](https://www.geeksforgeeks.org/java-and-multiple-inheritance/)。
假设我们有两个接口，方法名相同(geek)，返回类型不同(int 和 String)

```
public interface InterfaceX
{
    public int geek();
}
public interface InterfaceY
{
    public String geek();
}
```

现在，假设我们有一个实现这两个接口的类:

```
public class Testing implements InterfaceX, InterfaceY
{
public String geek()
    {
        return "hello";
    }
}
```

问题是:**一个 java 类可以实现两个具有相同方法的接口，这两个接口具有相同的签名但是返回类型不同吗？？**
**不，是错误**
如果两个接口包含一个签名相同但返回类型不同的方法，那么不可能同时实现两个接口。
根据 [JLS ( 8.4.2)](https://docs.oracle.com/javase/specs/jls/se8/html/jls-8.html#jls-8.4.2) 规定，这种情况下不允许使用相同签名的方法。

```
Two methods or constructors, M and N, have the same signature if they have,
the same name
the same type parameters (if any) (§8.4.4), and
after adopting the formal parameter types of N 
 to the type parameters of M, the same formal parameter types.
```

在类中声明两个具有重写等效签名的方法是一个编译时错误。

```
// JAVA program to illustrate the behavior
// of program when two interfaces having same 
// methods and different return-type
interface bishal
{
public
    void show();
}

interface geeks
{
public
    int show();
}

class Test implements bishal, geeks
{
    void show() // Overloaded method based on return type, Error
    {
    }
    int show() // Error
    {
        return 1;
    }
public
    static void main(String args[])
    {
    }
}
```

输出:

```
error: method show() is already defined in class Test
error: Test is not abstract and does not override abstract method show() in geeks
error: show() in Test cannot implement show() in bishal

```

```
// Java program to illustrate the behavior of the program
// when two interfaces having the same methods and different return-type
// and we defined the method in the child class
interface InterfaceA
{
public
    int fun();
}
interface InterfaceB
{
public
    String moreFun();
}

class MainClass implements InterfaceA, InterfaceB
{
public
    String getStuff()
    {
        return "one";
    }
}
```

```
error: MainClass is not abstract and does not override abstract method fun() in InterfaceA

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
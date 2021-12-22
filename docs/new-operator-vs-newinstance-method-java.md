# Java 中新运算符 vs newInstance()方法

> 原文:[https://www . geesforgeks . org/new-operator-vs-new instance-method-Java/](https://www.geeksforgeeks.org/new-operator-vs-newinstance-method-java/)

一般来说，new 运算符用于创建对象，但是如果我们想在运行时决定要创建的对象类型，就没有办法使用 new 运算符。在这种情况下，我们必须使用 newInstance()方法。考虑一个例子:

```java
// Java program to demonstrate working of newInstance()

// Sample classes
class A {  int a; }
class B {  int b; }

public class Test
{
    // This method creates an instance of class whose name is 
    // passed as a string 'c'.
    public static void fun(String c)  throws InstantiationException,
        IllegalAccessException, ClassNotFoundException
    {
        // Create an object of type 'c' 
        Object obj = Class.forName(c).newInstance();

        // This is to print type of object created
        System.out.println("Object created for class:"
                        + obj.getClass().getName());
    }

    // Driver code that calls main()
    public static void main(String[] args) throws InstantiationException,
    IllegalAccessException, ClassNotFoundException
    {
         fun("A");
    }   
}
```

输出:

```java
Object created for class:A

```

**Class.forName()** 方法返回类 **Class** 对象，我们正在对其调用 **newInstance()** 方法，该方法将返回我们作为命令行参数传递的那个类的对象。
如果通过的类不存在，则会出现**类未找到异常**。
**如果传递的类不包含默认构造函数，就会发生 instant exception**，因为 **newInstance()** 方法会在内部调用该特定类的默认构造函数。
**如果我们没有权限访问指定类定义的定义，就会出现 IllegalAccessException** 。

**相关文章:** [爪哇倒影](https://www.geeksforgeeks.org/reflection-in-java/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
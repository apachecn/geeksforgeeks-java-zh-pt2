# Java 中的私有构造函数和单例类

> 原文:[https://www . geesforgeks . org/private-constructors-and-singleton-class-in-Java/](https://www.geeksforgeeks.org/private-constructors-and-singleton-classes-in-java/)

我们先来分析下这个问题:

***我们可以有私有的构造函数吗？*T3】**

正如您很容易猜到的，像任何方法一样，我们可以为构造函数提供访问说明符。如果它是私有的，那么它只能在类内部访问。

***我们需要这样的‘私有构造函数’吗？*T3】**

我们可以在各种场景中使用私有构造函数。主要有

1.  [Internal constructor link]
2.  Class design pattern

***什么是 Singleton 类？*T3】**

顾名思义，如果一个类将该类的对象数量限制为一个，则称该类为单例。

对于这样的类，我们不能有一个以上的对象。

单例类广泛应用于网络和数据库连接等概念中。

**单体类的设计模式:**

singleton 类的构造函数是私有的，因此必须有另一种方法来获取该类的实例。使用类成员实例和工厂方法返回类成员可以解决这个问题。

下面是 java 中的一个例子，说明了同样的情况:

```
// Java program to demonstrate implementation of Singleton 
// pattern using private constructors.
import java.io.*;

class MySingleton
{
    static MySingleton instance = null;
    public int x = 10;

    // private constructor can't be accessed outside the class
    private MySingleton() {  }

    // Factory method to provide the users with instances
    static public MySingleton getInstance()
    {
        if (instance == null)        
             instance = new MySingleton();

        return instance;
    } 
}

// Driver Class
class Main
{
   public static void main(String args[])    
   {
       MySingleton a = MySingleton.getInstance();
       MySingleton b = MySingleton.getInstance();
       a.x = a.x + 10;
       System.out.println("Value of a.x = " + a.x);
       System.out.println("Value of b.x = " + b.x);
   }    
}
```

输出:

```
Value of a.x = 20
Value of b.x = 20
```

我们更改了 a.x 的值，b.x 的值也得到了更新，因为“a”和“b”都引用了同一个对象，也就是说，它们是单例类的对象。

本文由**阿舒托什·库马尔·辛格**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
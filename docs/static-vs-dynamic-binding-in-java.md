# Java 中静态绑定与动态绑定

> 原文:[https://www . geesforgeks . org/static-vs-dynamic-binding-in-Java/](https://www.geeksforgeeks.org/static-vs-dynamic-binding-in-java/)

**静态绑定:**编译器在编译时可以解析的绑定称为静态或早期绑定。所有静态、私有和最终方法的绑定都是在编译时完成的。

**为什么静态、最终和私有方法的绑定总是静态绑定？**
静态绑定在性能方面更好(不需要额外开销)。编译器知道所有这样的方法**不能被**覆盖，并且总是被本地类的对象访问。因此，编译器确定类的对象(当然是局部类)没有任何困难。这就是这种方法的绑定是静态的原因。
举个例子看看

```java
public class NewClass {
    public static class superclass {
        static void print()
        {
            System.out.println("print in superclass.");
        }
    }
    public static class subclass extends superclass {
        static void print()
        {
            System.out.println("print in subclass.");
        }
    }

    public static void main(String[] args)
    {
        superclass A = new superclass();
        superclass B = new subclass();
        A.print();
        B.print();
    }
}
```

在进一步向下滚动之前，猜猜上面程序的输出？

**输出**:

```java
print in superclass.
print in superclass.

```

可以看到，在这两种情况下都调用了超类的 print 方法。让我们看看这是如何发生的

*   我们已经用超类的引用创建了一个子类的对象和一个超类的对象。
*   由于超类的 print 方法是静态的，编译器知道它不会在子类中被覆盖，因此编译器知道在编译时调用哪个 print 方法，因此没有歧义。

*作为练习，读者可以将对象 B 的引用改为子类，然后检查输出。*

**动态绑定:**在动态绑定中编译器不决定要调用的方法。重写是动态绑定的一个完美例子。在重写时，父类和子类都有相同的方法。让我们通过一个例子来看看

```java
public class NewClass {
    public static class superclass {
        void print()
        {
            System.out.println("print in superclass.");
        }
    }

    public static class subclass extends superclass {
        @Override
        void print()
        {
            System.out.println("print in subclass.");
        }
    }

    public static void main(String[] args)
    {
        superclass A = new superclass();
        superclass B = new subclass();
        A.print();
        B.print();
    }
}
```

**输出:**

```java
print in superclass.
print in subclass.

```

这里输出不同。但是为什么呢？让我们分解代码并彻底理解它。

*   在这段代码中，方法不是静态的。
*   在编译期间，编译器不知道要调用哪个打印，因为编译器只通过引用变量而不是对象类型来进行，因此绑定将延迟到运行时，因此将基于对象类型调用打印的相应版本。

**重要点**

*   私有、最终和静态成员(方法和变量)使用静态绑定，而对于虚拟方法(在 Java 中，默认情况下方法是虚拟的)，绑定是在运行时基于运行时对象完成的。
*   静态绑定使用类型信息进行绑定，而动态绑定使用对象来解析绑定。
*   重载方法使用静态绑定来解析(当有多个同名方法时决定调用哪个方法)，而重写方法使用动态绑定，即在运行时。

本文由**里沙布·马赫塞供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
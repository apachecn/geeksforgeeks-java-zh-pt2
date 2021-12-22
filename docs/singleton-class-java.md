# Java 中的 Singleton 类

> 原文:[https://www.geeksforgeeks.org/singleton-class-java/](https://www.geeksforgeeks.org/singleton-class-java/)

在面向对象编程中，单例类是一次只能有一个对象(类的实例)的类。
第一次之后，如果我们尝试实例化 Singleton 类，新变量也会指向创建的第一个实例。因此，无论我们通过任何实例对类中的任何变量做什么修改，它都会影响所创建的单个实例的变量，并且如果我们通过定义的该类类型的任何变量访问该变量，它是可见的。

在将类定义为单例类时，也就是在设计单例类时，请记住以下要点:

1.  使构造函数私有。
2.  编写一个静态方法，它有这个单例类的返回类型对象。这里使用[惰性初始化](https://en.wikipedia.org/wiki/Lazy_initialization)的概念来编写这个静态方法。

让我们简单介绍一下单例类与 java 中的普通类有什么不同。这里的区别是在实例化方面，对于普通类，我们使用构造函数，而对于单例类，我们使用 [*getInstance()方法*](https://www.geeksforgeeks.org/java-signature-getinstance-method-with-examples/) ，我们将在示例 1 中查看，如下所示。一般来说，为了避免混淆，我们也可以在定义这个方法时使用类名作为方法名，如下例 2 所示。

**实施:**

**例 1**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program implementing Singleton class
// with using  getInstance() method

// Class 1
// Helper class
class Singleton {
    // Static variable reference of single_instance
    // of type Singleton
    private static Singleton single_instance = null;

    // Declaring a variable of type String
    public String s;

    // Constructor
    // Here we will be creating private constructor
    // restricted to this class itself
    private Singleton()
    {
        s = "Hello I am a string part of Singleton class";
    }

    // Static method
    // Static method to create instance of Singleton class
    public static Singleton getInstance()
    {
        if (single_instance == null)
            single_instance = new Singleton();

        return single_instance;
    }
}

// Class 2
// Main class
class GFG {
    // Main driver method
    public static void main(String args[])
    {
        // Instantiating Singleton class with variable x
        Singleton x = Singleton.getInstance();

        // Instantiating Singleton class with variable y
        Singleton y = Singleton.getInstance();

        // Instantiating Singleton class with variable z
        Singleton z = Singleton.getInstance();

        // Printing the hash code for above variable as
        // declared
        System.out.println("Hashcode of x is "
                           + x.hashCode());
        System.out.println("Hashcode of y is "
                           + y.hashCode());
        System.out.println("Hashcode of z is "
                           + z.hashCode());

        // Condition check
        if (x == y && y == z) {

            // Print statement
            System.out.println(
                "Three objects point to the same memory location on the heap i.e, to the same object");
        }

        else {
            // Print statement
            System.out.println(
                "Three objects DO NOT point to the same memory location on the heap");
        }
    }
}
```

**Output**

```java
Hashcode of x is 558638686
Hashcode of y is 558638686
Hashcode of z is 558638686
Three objects point to the same memory location on the heap i.e, to the same object
```

输出解释:

![Singleton class](img/d706702b3f5715b7cf582540abbc55a0.png)

在单例类中，当我们第一次调用 ***getInstance()方法*** 时，它会创建一个名为 single_instance 的类的对象，并将其返回给变量。由于 single_instance 是静态的，因此它会从 null 更改为某个对象。下一次，如果我们尝试调用 getInstance()方法，由于 single_instance 不为 null，它将返回到变量，而不是再次实例化 Singleton 类。这部分由 if 条件完成。
在主类中，我们通过调用 static *方法 getInstance()* 来实例化带有 3 个对象 x，y，z 的 singleton 类。但是实际上在创建对象 x 之后，变量 y 和 z 指向对象 x，如图所示。因此，如果我们改变对象 x 的变量，这反映在我们访问对象 y 和 z 的变量时。同样，如果我们改变对象 z 的变量，这反映在我们访问对象 x 和 y 的变量时。
现在我们已经完成了覆盖示例 1 的所有方面，并且已经实现了相同的方面，现在我们将实现方法名与类名相同的 Singleton 类。

**例 2**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program implementing Singleton class
// with method name as that of class

// Class 1
// Helper class
class Singleton {
    // Static variable single_instance of type Singleton
    private static Singleton single_instance = null;

    // Declaring a variable of type String
    public String s;

    // Constructor of this class
    // Here private constructor is is used to
    // restricted to this class itself
    private Singleton()
    {
        s = "Hello I am a string part of Singleton class";
    }

    // Method
    // Static method to create instance of Singleton class
    public static Singleton Singleton()
    {
        // To ensure only one instance is created
        if (single_instance == null) {
            single_instance = new Singleton();
        }
        return single_instance;
    }
}

// Class 2
// Main class
class GFG {
    // Main driver method
    public static void main(String args[])
    {
        // Instantiating Singleton class with variable x
        Singleton x = Singleton.Singleton();

        // Instantiating Singleton class with variable y
        Singleton y = Singleton.Singleton();

        // instantiating Singleton class with variable z
        Singleton z = Singleton.Singleton();

        // Now  changing variable of instance x
        // via toUpperCase() method
        x.s = (x.s).toUpperCase();

        // Print and display commands
        System.out.println("String from x is " + x.s);
        System.out.println("String from y is " + y.s);
        System.out.println("String from z is " + z.s);
        System.out.println("\n");

        // Now again changing variable of instance x
        z.s = (z.s).toLowerCase();

        System.out.println("String from x is " + x.s);
        System.out.println("String from y is " + y.s);
        System.out.println("String from z is " + z.s);
    }
}
```

**Output**

```java
String from x is HELLO I AM A STRING PART OF SINGLETON CLASS
String from y is HELLO I AM A STRING PART OF SINGLETON CLASS
String from z is HELLO I AM A STRING PART OF SINGLETON CLASS

String from x is hello i am a string part of singleton class
String from y is hello i am a string part of singleton class
String from z is hello i am a string part of singleton class
```

输出解释:

在 singleton 类中，当我们第一次调用 Singleton()方法时，它会创建一个名为 Singleton _ instance 的 Singleton 类的对象，并将其返回给变量。由于 single_instance 是静态的，因此它会从 null 更改为某个对象。下一次，如果我们尝试调用 Singleton()方法，由于 single_instance 不为 null，它将返回到变量，而不是再次实例化 Singleton 类。

本文由 **Pavan Gopal Rayapati** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
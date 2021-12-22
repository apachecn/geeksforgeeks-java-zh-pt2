# 为什么一个构造函数在 Java 中不能是最终的、静态的或者抽象的？

> 原文:[https://www . geesforgeks . org/why-a-constructor-can-final-static-or-abstract-in-Java/](https://www.geeksforgeeks.org/why-a-constructor-can-not-be-final-static-or-abstract-in-java/)

**先决条件:**[Java 中的继承](https://www.geeksforgeeks.org/inheritance-in-java/)

[java 中的 Constructor](https://www.geeksforgeeks.org/constructors-in-java/) 是一种不同于普通 Java 方法/普通方法的特殊类型的方法。构造函数用于初始化对象。创建类的对象时，会自动调用构造函数。它在语法上类似于一个方法，但是它与它的类同名，并且构造函数没有返回类型。

**Java 构造函数不能是最终的**

java 构造函数的一个重要属性就是不能是 [final](https://www.geeksforgeeks.org/final-keyword-java/) 。我们知道，[构造函数在 java](https://www.geeksforgeeks.org/constructors-not-inherited-java/) 中是没有继承的。因此，施工人员不受隐藏或[超越](https://www.geeksforgeeks.org/overriding-in-java/#:~:text=In%20any%20object%2Doriented%20programming,super%2Dclasses%20or%20parent%20classes.&text=Method%20overriding%20is%20one%20of,java%20achieve%20Run%20Time%20Polymorphism.)的影响。当没有构造函数重写的机会时，也就没有修改的机会。当没有修改的机会时，就没有限制修改的意义了。我们知道 final 关键字限制了进一步的修改。所以一个 java 构造函数不可能是最终的，因为它本身是不可修改的。此外，java 构造函数在内部是最终的。所以也没有必要再做最后的声明了。

**示例:**假设我们将一个 java 构造函数声明为 final，现在让我们看看发生了什么。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Constructor as final

import java.io.*;
class GFG {

    // GFG() constructor is declared final
    final GFG()
    {
        // This line can not be executed as compile error
        // will come
        System.out.print(
            "Hey you have declared constructor as final, it's error");
    }
}
class Main {
    public static void main(String[] args)
    {
        // Object of GFG class created
        // Automatically GFG() constructor called
        GFG obj = new GFG();
    }
}
```

**输出:**

```java
prog.java:4: error: modifier final not allowed here
final GFG( )
      ^
1 error
```

从上面的例子也很清楚，如果我们将构造函数定义为 final，编译器将给出一个错误，因为**修饰符 final 是不允许的**。

**Java 构造函数不能是静态的**

java 构造函数的一个重要属性是它不能是[静态的](https://www.geeksforgeeks.org/static-keyword-java/)。我们知道 static 关键字属于一个类，而不是一个类的对象。创建类的对象时会调用构造函数，因此不使用静态构造函数。另一件事是，如果我们将声明静态构造函数，那么我们不能从子类访问/调用构造函数。因为我们知道静态在一个类中是允许的，但是子类不允许。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java class and a subclass

import java.io.*;

class GFG {
    public GFG()
    {
        // Constructor of GFG class
        System.out.println("GFG Constructor");
    }
}
class SubClass extends GFG {

    SubClass()
    {
        // Constructor of SubClass class
        // By default super() is hidden here
        // So Super class i.e GFG class constructor called
        System.out.println("Subclass Constructor");
    }
    public static void main(String args[])
    {
        // SubClass class object created
        // Automatically SubClass() constructor called
        SubClass obj = new SubClass();
    }
}
```

**Output**

```java
GFG Constructor
Subclass Constructor
```

上面的例子表明，当创建子类的对象时，子类构造函数通过构造函数链调用超类构造函数。但是如果我们使超类构造函数成为静态的，那么它就不能像上面所说的那样被子类*静态调用，它可以在类内访问，但是不能被*子类*访问。*

不将构造函数声明为静态的一个更重要的原因是，我们知道静态成员在程序中首先被执行，就像静态的主方法首先被执行一样。但是每次创建对象时都会调用构造函数。但是如果我们将它声明为静态的，那么构造函数将在对象创建之前被调用。所以一般来说，如果我们看到 static 和 constructor 是相反的，如果我们想为实例变量赋值初始值，我们可以使用 constructor，如果我们想赋值静态变量，我们可以使用[静态块。](https://www.geeksforgeeks.org/g-fact-79/)

**示例:**假设我们将一个 java 构造函数声明为静态的，现在让我们看看发生了什么。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java constructor as static

import java.io.*;

class GFG {

    // GFG() constructor is declared static
    static GFG()
    {
        // This line can not be executed as it compile error
        // will come
        System.out.print(
            "Hey you have declared constructor as static, it's error");
    }
}
class Main {
    public static void main(String[] args)
    {
        // Object of GFG class created
        // Automatically GFG() constructor called
        GFG obj = new GFG();
    }
}
```

**输出**

```java
prog.java:5: error: modifier static not allowed here
 static GFG( )
        ^
1 error
```

从上面的例子也很清楚，如果我们将构造函数定义为静态的，编译器会给出一个错误，因为**修饰符静态是不允许的。**

**Java 构造函数不能抽象**

java 构造函数的一个重要属性就是不能[抽象](https://www.geeksforgeeks.org/abstract-keyword-in-java/)。如果我们声明一个构造函数是抽象的，因为我们必须在子类中实现它，但是我们知道当使用 new 关键字时，构造函数是隐式调用的，所以它不能缺少主体，也不能作为普通方法调用。此外，如果我们将构造函数抽象化，那么我们必须稍后提供主体。但是我们知道构造函数不能被覆盖，所以提供主体是不可能的。因此，当我们不能为它提供实现时，我们将如何处理这个抽象构造函数。

**示例:**假设我们将一个 java 构造函数声明为抽象的，现在让我们看看发生了什么。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java constructor as static

import java.io.*;
abstract class GFG {

    // GFG() constructor is declared abstract
    abstract GFG()
    {
        // This line can not be executed as compile error
        // will come
        System.out.print(
            "Hey you have declared constructor as abstract, it's error");
    }
}
class Main {
    public static void main(String[] args)
    {
        // Object of GFG class created
        // Automatically GFG() constructor should be called
        // But object creation in abstract class is error
        GFG obj = new GFG();
    }
}
```

**输出**

```java
prog.java:5: error: modifier abstract not allowed here
 abstract GFG( )
          ^
prog.java:17: error: GFG is abstract; cannot be instantiated
   GFG obj = new GFG();
             ^
2 errors
```

从上面的例子也很清楚，如果我们将构造函数定义为静态的，编译器将给出一个错误，因为**修饰符抽象是不允许的。**

**注意:** [Java 接口不能有构造函数，但是抽象类可以有构造函数。](https://www.geeksforgeeks.org/why-java-interfaces-cannot-have-constructor-but-abstract-classes-can-have/)
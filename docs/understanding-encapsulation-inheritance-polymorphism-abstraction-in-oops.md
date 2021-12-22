# 理解 OOPs 中的封装、继承、多态、抽象

> 原文:[https://www . geesforgeks . org/understanding-封装-继承-多态-抽象-in-oops/](https://www.geeksforgeeks.org/understanding-encapsulation-inheritance-polymorphism-abstraction-in-oops/)

顾名思义，[面向对象编程或 OOPs](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/) 是指在编程中使用[对象](https://www.geeksforgeeks.org/classes-objects-java/)的语言。面向对象编程的目标是在编程中实现真实世界的实体，如继承、隐藏、多态等。OOP 的主要目的是将数据和对数据进行操作的函数绑定在一起，这样除了函数之外，代码的任何其他部分都不能访问这些数据。在本文中，我们将通过一个例子来理解面向对象的所有概念。

让我们假设我们有一个鸟类类，我们正在创建一个鸟类列表。让我们理解一下在这个鸟的创作中使用的面向对象的概念。

**[继承](https://www.geeksforgeeks.org/inheritance-in-java/) :** 对于任何鸟类，都有一组预定义的属性，这些属性对所有鸟类都是通用的，并且有一组特定于特定鸟类的属性。因此，从直觉上，我们可以说所有的鸟类都继承了翅膀、腿、眼睛等共同的特征。因此，以面向对象的方式表示鸟，我们首先声明一个鸟类，它有一组所有鸟共有的属性。通过这样做，我们可以避免在我们创建的每只鸟中声明这些公共属性。相反，我们可以简单地*继承*我们创造的所有鸟类中的鸟类。下面是一个如何实现继承概念的例子。

```
// Java program to demonstrate
// the bird class

// Implementing the bird class
public class Bird {

    // Few properties which
    // define the bird
    String color;
    int legs;

    // Few operations which the
    // bird performs
    public void eat()
    {
        System.out.println(
            "This bird has eaten");
    }

    public void fly()
    {
        System.outp.println(
            "This bird is flying");
    }
}
```

在实现了 bird 类之后，如果我们希望创建一只鸽子，那么我们只需继承上面的 Bird 类。

```
// Java program to demonstrate the
// Inheritance

// Creating the Pigeon class which
// extends the bird class
public class Pigeon extends Bird {

    // Overriding the fly method
    // which makes this pigeon fly
    public void fly()
    {
        System.out.println(
            "Pigeon flys!!!!");
    }
}
```

**[封装](https://www.geeksforgeeks.org/encapsulation-in-java/) :** 现在，我们已经定义了鸟类的属性，并且可以通过创建鸟类的对象来初始化鸟所具有的属性，如颜色、翅膀、腿。然而，如果我们仅仅能够通过对象的引用来改变 bird 类的属性，那么属性就失去了最初初始化时的信息。

例如，假设我们最初通过创建构造函数创建了一只灰色的鸽子，任何拥有鸽子对象实例的用户都可以通过简单地用“this”关键字引用属性来将这种颜色更改为红色或黑色。因此，为了避免这种情况，我们将属性包含在方法中。这些方法被称为属性的获取者和设置者。其思想是简单地将属性的初始化和检索包含在一个方法中，而不是直接引用属性。这也提供了一个优势，因为设置器让我们可以完全控制属性的值设置，并帮助我们限制不必要的更改。例如，如果一只鸽子被创造(出生)成灰色，它直到鸽子死去才改变。因此，正在使用的用户不应该按照自己的意愿改变颜色。下面是上述 Bird 类的获取器和设置器的实现。

```
// Java program to demonstrate
// the bird class

// Implementing the bird class
public class Bird {

    // Few properties which
    // define the bird
    String color;
    int legs;

    // Implementing the getters and
    // setters for the color and legs.

    public void setColor(String color)
    {
        this.color = color;
    }

    public String getColor()
    {
        return this.color;
    }

    public void setLegs(String legs)
    {
        this.legs = legs;
    }

    public String getLegs()
    {
        return this.legs;
    }

    // Few operations which the
    // bird performs
    public void eat()
    {
        System.out.println(
            "This bird has eaten");
    }

    public void fly()
    {
        System.outp.println(
            "This bird is flying");
    }
}
```

**[多态](https://www.geeksforgeeks.org/polymorphism-in-java/) :** 多态这个词是由 poly 和 morph 两个词组成的，其中 poly 表示多，morph 表示形式。在编程中，多态性是一种允许一个接口用于一类通用动作的特性。在上述鸟和鸽子的概念中，鸽子天生就是鸟。此外，如果将鸟类进一步分为多种类别，如飞禽、不会飞的鸟类等。鸽子也属于飞禽的范畴。此外，如果动物类被进一步分类为食草动物和食肉动物，鸽子又会被归入食草动物的范畴。因此，多态的思想是同一个对象采取多种形式的能力。多态性有两种类型:

1.  **编译时多态性:**又称静态多态性。这种类型的多态性是通过函数重载或运算符重载实现的。当我们用不同的签名定义多个方法，并且编译器根据方法签名知道需要执行哪个方法时，就会出现这种情况。
2.  **[运行时多态](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/) :** 也叫动态方法调度。这是一个在运行时解析对被重写方法的函数调用的过程。这种类型的多态性是通过方法重写实现的。当具有相同参数的相同方法被不同的上下文重写时，编译器不知道该方法被重写。它只是检查方法是否存在，并在运行时执行已经被覆盖的函数。

在 java 中，我们还可以[向上转换和向下转换](https://www.geeksforgeeks.org/upcasting-vs-downcasting-in-java/)对象。这个概念背后的核心思想也是多态性。这个想法是，鸟的对象可以有鸽子的价值，因为它继承了鸟的特征。因此，如果父对象和子对象以下列方式相互扩展，父对象也可以用子属性初始化:

> 鸟 b =新鸽()；

**[抽象](https://www.geeksforgeeks.org/abstraction-in-java-2/) :** 抽象一般指隐藏。在上面的鸟和鸽子的场景中，假设有一个用户想看鸽子飞。用户只是对看到鸽子飞感兴趣，而对鸟实际上是如何飞的不感兴趣。因此，在用户希望让它飞起来的上述场景中，他将简单地通过使用**鸽.飞()**来调用飞的方法，其中鸽是鸟鸽的对象。因此，抽象是指在不考虑背景细节的情况下表现本质特征的艺术。在 Java 中，抽象是通过使用[接口](https://www.geeksforgeeks.org/interfaces-in-java/)和[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)来实现的。我们可以使用接口实现完全的抽象，而使用抽象类可以实现部分或完全的抽象。抽象被认为是重要概念之一的原因是:

1.  它降低了观察事物的复杂性。
2.  避免代码重复并提高可重用性。
3.  有助于提高应用程序或程序的安全性，因为只有重要的细节才提供给用户。
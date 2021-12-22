# Java 中的超级关键词

> 原文:[https://www.geeksforgeeks.org/super-keyword/](https://www.geeksforgeeks.org/super-keyword/)

java 中的 **super** 关键字是一个引用变量，用于引用父类对象。关键词“超级”带着传承的概念进入画面。它主要用于以下情况:

**1。使用带变量的 super:**当派生类和基类具有相同的数据成员时，会出现这种情况。在这种情况下，JVM 可能会出现歧义。使用这个代码片段，我们可以更清楚地理解它:

```
/* Base class vehicle */
class Vehicle
{
    int maxSpeed = 120;
}

/* sub class Car extending vehicle */
class Car extends Vehicle
{
    int maxSpeed = 180;

    void display()
    {
        /* print maxSpeed of base class (vehicle) */
        System.out.println("Maximum Speed: " + super.maxSpeed);
    }
}

/* Driver program to test */
class Test
{
    public static void main(String[] args)
    {
        Car small = new Car();
        small.display();
    }
}
```

输出:

```
Maximum Speed: 120
```

在上面的例子中，基类和子类都有一个成员 maxSpeed。我们可以使用 super 关键字在子类中访问基类的 maxSpeed。

**2。使用 super with 方法:**当我们想要调用父类方法时使用这个方法。因此，每当父类和子类有相同的命名方法时，为了解决歧义，我们使用 super 关键字。这段代码有助于理解 super 关键字的用法。

```
/* Base class Person */
class Person
{
    void message()
    {
        System.out.println("This is person class");
    }
}

/* Subclass Student */
class Student extends Person
{
    void message()
    {
        System.out.println("This is student class");
    }

    // Note that display() is only in Student class
    void display()
    {
        // will invoke or call current class message() method
        message();

        // will invoke or call parent class message() method
        super.message();
    }
}

/* Driver program to test */
class Test
{
    public static void main(String args[])
    {
        Student s = new Student();

        // calling display() of Student
        s.display();
    }
}
```

输出:

```
This is student class
This is person class
```

在上面的例子中，我们已经看到，如果我们只调用方法 message()，那么就会调用当前类 message()，但是使用 super 关键字，也可以调用超类的 message()。

**3** 。**使用带构造函数的 super:**super 关键字也可以用来访问父类构造函数。更重要的是，' ' super '可以根据情况同时调用参数和非参数构造函数。下面是解释上述概念的代码片段:

```
/* superclass Person */
class Person
{
    Person()
    {
        System.out.println("Person class Constructor");
    }
}

/* subclass Student extending the Person class */
class Student extends Person
{
    Student()
    {
        // invoke or call parent class constructor
        super();

        System.out.println("Student class Constructor");
    }
}

/* Driver program to test*/
class Test
{
    public static void main(String[] args)
    {
        Student s = new Student();
    }
}
```

输出:

```
Person class Constructor
Student class Constructor
```

在上面的例子中，我们通过子类构造函数使用关键字“super”调用了超类构造函数。

**其他要点:**

1.  The call to super () must be the first statement in the derived (student) class constructor.
2.  If the constructor does not explicitly call the superclass constructor, the Java compiler will automatically insert the call to the parameterless constructor of the superclass. If the superclass does not have a parameterless constructor, you will get a compile-time error. There is no such constructor for Object 【T0], so if Object is the only superclass, there is no problem.
3.  If the constructor of a subclass explicitly or implicitly calls the constructor of its superclass, you may think that the whole constructor chain is called, all the way to the constructor of the object. Actually, it is. Called *constructor link* ..

本文由 **[维斯瓦吉特·斯里瓦斯塔瓦](https://in.linkedin.com/pub/vishwajeet-srivastava/85/80a/9ba)** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
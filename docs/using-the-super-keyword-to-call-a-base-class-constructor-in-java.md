# 在 Java 中使用超级关键字调用基类构造函数

> 原文:[https://www . geesforgeks . org/使用-super-关键字调用 java 中的基类构造函数/](https://www.geeksforgeeks.org/using-the-super-keyword-to-call-a-base-class-constructor-in-java/)

我们更喜欢 [**继承**](https://www.geeksforgeeks.org/inheritance-in-java/) 来重用现有类中可用的代码。在 Java 中，继承是一个类继承另一个类的属性的概念。在下面的例子中，有两个类编程和动态规划，而编程是父类，动态规划是子类。从主类中，我们创建了一个 DP 的对象，即子类，因为它也允许我们从它的父类中访问方法，但是如果我们创建了一个父类(编程)的对象，那么我们就不能从它的子类中访问方法或对象。

创建子类的对象后，我们首先从子类调用一个方法，然后从父类调用一个方法。这并不重要，因为我们可以以任何顺序调用对象。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate inheritance properties

class Programming {

    // Creating method m1 for class Programming
    public void m1()
    {
      System.out.println("Programming");
    }
}
class DP extends Programming {

    // Creating method m2 for class DP
    public void m2()
    {
      System.out.println("DP");
    }
}
public class GFG {

    public static void main(String[] args)
    {
        // Creating Obj for Class DP and
        // Calling both m1 from class programming
        // And calling m2 from class DP respectively.
        DP obj = new DP();
        obj.m2();
        obj.m1();
    }
}
```

**输出:**

```
DP
Programming
```

### [建造师](https://www.geeksforgeeks.org/constructors-in-java/) [传承](https://www.geeksforgeeks.org/inheritance-in-java/)

在下面的例子中，我们已经创建了一个父类和子类。在这里，我们已经创建了一个子类的对象，因为构造函数将在创建一个我们不需要提及的对象时调用自己。

创建子类的对象后，构造函数应该打印它自己的类的输出，但是从输出中，我们可以识别出父类被执行了，然后子类被执行了，这是因为我们为继承类创建了一个构造函数，默认情况下每个类都包含一个 super()，因为我们在调用继承类时，它的第一行包含 super()并调用了 Parent 类。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the concept of Constructor
// inheritance.

// Base Class
class Programming {

    // Constructor for class Programming
    public Programming()
    {
        System.out.println("Programming");
    }
}

// Child Class inherit the Base
// Class
class DP extends Programming {

    // Constructor for class DP
    public DP() { System.out.println("DP"); }
}

// Main Class
public class GFG {

    public static void main(String[] args)
    {
        // Creating obj for
        // class DP
        DP obj = new DP();
    }
}
```

**Output**

```
Programming
DP
```

### [建造师超载](https://www.geeksforgeeks.org/constructor-overloading-java/)带[超](https://www.geeksforgeeks.org/super-keyword/)

在下面的例子中，我们使用了构造函数重载的概念，我们创建了一个子类的对象，在调用子类的构造函数后，它的第一行是 super(10，20)，表示从父类调用匹配的构造函数，如果我们没有提到那一行，默认情况下，它调用 super()而没有从父类调用参数化的构造函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the concepts of constructor
// overloading.

// Base Class
class Programming {

    // Creating Constructor for
    // class Programming.
    public Programming()
    {
        System.out.println("Programming");
    }

    // Parameterized Constructor
    public Programming(int i, int j)
    {
        System.out.println("Programming + +");
    }
}

// Child Class
class DP extends Programming {

    public DP()
    {
        // Calling by using
        // Programming(int i,int j)
        // from class Programming.
        super(10, 20);
        System.out.println("DP");
    }

    // Parameterized Constructor
    // for class DP
    public DP(int i, int j)
    {
        System.out.println("DP + +");
    }
}

// Main Class
public class GFG {
    public static void main(String[] args)
    {
        // Creating Object for class DP.
        DP obj = new DP();
    }
}
```

**输出:**

```
Programming + +
DP
```

### 类似

让我们看看下面的片段，

*   在下面的代码中，我们已经创建了一个子类的对象，我们从对象行本身传递值 10，在转到特定的构造函数之后，默认情况下，它首先调用 super()，并从父类打印“Programming”。
*   需要注意的一点是，这里我们从对象创建行调用参数化构造函数，但是默认情况下它将调用 super()，这在默认情况下是可用的。
*   在子类中，我们也可以给 super()加上参数，从父类中调用特定的构造函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Base Class
class Programming {

    // Default Constructor
    public Programming()
    {
        System.out.println("Programming");
    }

    // parameterized Constructor
    public Programming(int i, int j)
    {
        System.out.println("Programming + +");
    }
}
class DP extends Programming {

    public DP() { System.out.println("DP"); }

    // parameterized Constructor with
    // one parameter
    public DP(int i) { System.out.println("DP +"); }

    // parameterized Constructor with
    // two parameter i and j.
    public DP(int i, int j)
    {
        System.out.println("DP + +");
    }
}

// Main Class
public class GFG {

    public static void main(String[] args)
    {

        // Creating obj for DP
        // class which inherits the
        // properties of class programming
        DP obj = new DP(10);
    }
}
```

**输出:**

```
Programming
DP +
```
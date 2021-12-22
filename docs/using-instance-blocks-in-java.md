# 在 Java 中使用实例块

> 原文:[https://www . geesforgeks . org/using-instance-blocks-in-Java/](https://www.geeksforgeeks.org/using-instance-blocks-in-java/)

实例块可以被定义为 java 中的无名方法，我们可以在其中定义逻辑，它们具有如下某些特性。它们可以在类中声明，但不能在任何方法中声明。实例块逻辑对所有对象都是通用的。实例块在创建过程中只对每个对象执行一次。

插图:

```java
class GFG {
    {
        // Code inside instance block
    }
}
```

**实例块的优势如下:**

每当创建任何类型的对象时，都会执行实例块。如果我们想编写一个逻辑，我们想在创建各种对象时执行，那么使用实例块是一个好主意，可以避免在每个构造函数中编写相同的逻辑。

**实例块的缺点如下:**

我们通常不使用它们来初始化对象，因为它们不能接受参数。如果我们仍然使用实例块来进行初始化，那么所有的对象都必须用实际上无用的相同值来初始化。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Usage of Instance Blocks

// Class 1
// Helper class
class GFG {

    // Constructors of this class

    // Constructor 1
    // This constructor will get executed for 1st
    // kind of object
    GFG()
    {
        System.out.println("1st argument constructor");
    }

    // Constructor 2
    // This constructor will get executed for
    // 2nd kind of object
    GFG(String a)
    {

        // Print statement when this constructor is called
        System.out.println("2nd argument constructor");
    }

    // Constructor 3
    // This constructor will get executed
    // for 3rd kind of object
    GFG(int a, int b)
    {

        // Print statement when this constructor is called
        System.out.println("3rd arguments constructor");
    }

    {
        // Creation of an instance block
        System.out.println("Instance block");
    }
}

// Class 2
// Main class
class GFGJava {

    // main driver method
    public static void main(String[] args)
    {

        // Object of 1st kind
        new GFG();

        // Object of 2nd kind
        new GFG("I like Java");

        // Object of 3rd kind
        new GFG(10, 20);
    }
}
```

**Output**

```java
Instance block
1st argument constructor
Instance block
2nd argument constructor
Instance block
3rd arguments constructor
```

> **注意:**实例块的执行顺序遵循顺序——静态块、实例块和构造函数。\\

从下面提出的例子可以证明这一点:

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Execution of Instance Blocks

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Making object of class in main()
        GFG geek = new GFG();
    }

    // Constructor of this class
    GFG()
    {

        // Print statement when constructor is called
        System.out.println("I am Constructor!");
    }
    {
        // Print statement when instance block is called
        System.out.println("I am Instance block!");
    }

    static
    {

        // Print statement when static block is called
        System.out.println("I am Static block!");
    }
}
```

**Output**

```java
I am Static block!
I am Instance block!
I am Constructor!
```
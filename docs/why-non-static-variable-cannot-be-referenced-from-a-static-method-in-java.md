# 为什么 Java 中的静态方法不能引用非静态变量

> 原文:[https://www . geesforgeks . org/why-非静态变量-不能从静态方法中引用-java/](https://www.geeksforgeeks.org/why-non-static-variable-cannot-be-referenced-from-a-static-method-in-java/)

Java 是最流行、应用最广泛的编程语言和平台之一。Java 是[面向对象](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)。但是，它不被认为是纯面向对象的，因为它支持原始数据类型(如 int、char 等)。在 java 中，方法可以声明为静态或非静态的。在本文中，让我们讨论为什么不能从静态方法中引用非静态变量。
在进入错误之前，让我们先了解每种方法的含义:

*   **Static Method:** 静态方法是属于某个类的方法，但它不属于该类的实例，可以在没有该类的实例或对象的情况下调用该方法。在静态方法中，该方法只能访问另一个类或同一类的静态数据成员和静态方法，但不能访问非静态方法和变量。
*   **非静态方法:**任何定义不包含 static 关键字的方法都是非静态方法。在非静态方法中，该方法可以访问静态数据成员和静态方法以及另一个类或同一类的非静态成员和方法，也可以更改任何静态数据成员的值。

**<u>从静态上下文引用非静态变量有什么问题？</u>**
让我们考虑下面的代码，其中用一个非静态变量和一个静态方法创建了类 A。该类的对象正在另一个类中创建，静态方法的访问方式如下:

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to demonstrate
// why a non-static variable cannot
// be accessed from a static context

// Creating a class A
class A {

    // A non-static variable
    int N;

    // Static method
    public static void increment()
    {
          // this throws a compile - time error.     
        N++;
    }
}

public class Demo {

    // Main method
    public static void main(String args[])
    {
        // Creating multiple objects
        // for class A
        A obj1 = new A();
        A obj2 = new A();
        A obj3 = new A();

        // Assigning the different values
        // for the non static variable N
        obj1.N = 3;
        obj2.N = 4;
        obj3.N = 5;

        // Calling the method
        A.increment();

        System.out.println(obj1.N);
        System.out.println(obj2.N);
        System.out.println(obj3.N);
    }
}
```

如果这段代码真的可以运行，您会期望输出是:

```
4
5
6

```

**但是却抛出了一个编译时错误**T2】

```
Compile Errors:

prog.java:16: error: non-static variable N cannot be referenced from a static context
        N++;
        ^
1 error

```

我们可以看到上面的程序给出了错误。虽然在上面的代码中，所有的对象名都有相同的变量名 N，但是如果我们试图增加 N，就会产生一个错误。这个错误在[面向对象编程](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)中非常常见。
**<u>为什么会出现这种错误？</u>**
对于非静态变量，需要一个对象实例来调用变量。我们还可以通过为非静态变量分配不同的值来创建多个对象。因此，不同的对象对同一个变量可能有不同的值。在上面的程序中，我们为**A 类**创建了三个对象 **obj1** 、 **obj2** 、 **obj3** ，并分别为对象 **obj1** 、 **obj2** 、 **obj3** 分配了三个不同的值 **3、 **4** 、 **5** 。当我们试图调用**函数增量**时，由于 **N** 的每个对象都有自己的值，编译器将无法理解该方法应该将该值增量为 N 的什么值。
**<u>如何解决这个错误？</u>**
为了避免歧义，java 编译器抛出了一个**编译时**错误。因此，这个问题可以通过用对象名处理变量来解决。简而言之，我们总是需要创建一个对象，以便从静态上下文中引用一个非静态变量。每当创建新实例时，都会创建所有非静态变量和方法的新副本。通过使用新实例的引用，可以访问这些变量。例如:** 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to access a
// non static variable from
// a static block
public class GFG {

    int count = 0;

    // Driver code
    public static void main(String args[])
    {

        // Accessing static variable
        // by creating an instance
        // of the class
        GFG test = new GFG();

        test.count++;
        System.out.println(test.count);
    }
}
```

**Output**

```
1

```
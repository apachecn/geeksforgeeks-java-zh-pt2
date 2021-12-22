# 为什么 Java 接口不能有构造函数，而抽象类可以有？

> 原文:[https://www . geesforgeks . org/why-Java-interfaces-不能有-constructor-但-abstract-class-可以有/](https://www.geeksforgeeks.org/why-java-interfaces-cannot-have-constructor-but-abstract-classes-can-have/)

**先决条件:**Java 中的[接口](https://www.geeksforgeeks.org/interfaces-in-java/)和[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)。

一个[构造器](https://www.geeksforgeeks.org/constructors-in-java/) 是一个特殊的成员函数，用来初始化新创建的对象。当一个类的对象被创建时，它被自动调用。

**为什么接口不能有构造函数？**

*   An interface is a completely abstract class. By default, all data members in the interface are public, static, and final. All static final fields must be assigned values when they are declared, otherwise a compilation error will be thrown, saying that " *variable **variable _ name** in the default constructor is not initialized".*
*   The internal method of the interface defaults to public abstraction, which means that the method implementation cannot be provided by the interface itself, but must be provided by the implementation class. Therefore, there is no need to have a constructor inside the interface.
*   Constructors are used to initialize non-static data members. Because there are no non-static data members in the interface, constructors are not needed.
*   The methods in the interface only declare that they are not defined. Because there is no method implementation, there is no need to make objects for calling methods in the interface, so there is no meaning of constructors.
*   If we try to create a constructor inside the interface, the compiler will give a compile-time error.

## 爪哇

```
// Java program that demonstrates why
// interface can not have a constructor

// Creating an interface
interface Subtraction {

    // Creating a method, by default
    // this is a abstract method
    int subtract(int a, int b);
}

// Creating a class that implements
// the Subtraction interface
class GFG implements Subtraction {

    // Defining subtract method
    public int subtract(int a, int b)
    {
        int k = a - b;
        return k;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Creating an instance of
        // GFG class
        GFG g = new GFG();
        System.out.println(g.subtract(20, 5));
    }
}
```

**输出**

```
15
```
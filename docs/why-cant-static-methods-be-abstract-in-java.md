# 为什么静态方法在 Java 中不能抽象？

> 原文:[https://www . geesforgeks . org/why-cant-static-methods-be-abstract-in-Java/](https://www.geeksforgeeks.org/why-cant-static-methods-be-abstract-in-java/)

在 Java 中，**静态方法不能是抽象的**。这样做会导致编译错误。
**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// abstract static method

import java.io.*;

// super-class A
abstract class A {

    // abstract static method func
    // it has no body
    abstract static void func();
}

// subclass class B
class B extends A {

    // class B must override func() method
    static void func()
    {
        System.out.println(
            "Static abstract"
            + " method implemented.");
    }
}

// Driver class
public class Demo {
    public static void main(String args[])
    {

        // Calling the abstract
        // static method func()
        B.func();
    }
}
```

上面的代码不正确，因为静态方法不能是抽象的。运行时出现的编译错误为:
**编译错误:**

```java
prog.java:12: error: illegal combination of modifiers: abstract and static
    abstract static void func();
                         ^
1 error
```

**<u>如果一个静态方法被抽象会发生什么？</u>**
假设我们做一个静态的方法抽象。那么该方法将被写成:

```java
public abstract static void func();
```

*   **Scenario 1:** When a method is described as abstract by using the abstract type modifier, it becomes responsibility of the subclass to implement it because they have no specified implementation in the super-class. Thus, a subclass must override them to provide method definition. 
*   **场景 2:** 现在当一个方法被描述为静态的时候，就明确了这个静态方法不能被任何子类覆盖(它使静态方法隐藏起来)，因为静态成员是编译时元素，覆盖它们会使它成为运行时元素(runtime 多态)。

现在考虑**场景 1** ，如果 func 方法被描述为抽象的，那么它必须在子类中有一个定义。但是根据**场景 2** ，静态 func 方法不能在任何子类中被覆盖，因此它不能有定义。所以这些情景似乎相互矛盾。因此，我们关于静态函数方法是抽象的假设失败了。**所以，一个静态的方法不能是抽象的**。
那么该方法将被编码为:

```java
public static void func();
```

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// abstract static method

import java.io.*;

// super-class A
abstract class A {

    // static method func
    static void func()
    {
        System.out.println(
            "Static method implemented.");
    }

    // abstract method func1
    // it has no body
    abstract void func1();
}

// subclass class B
class B extends A {

    // class B must override func1() method
    void func1()
    {
        System.out.println(
            "Abstract method implemented.");
    }
}

// Driver class
public class Demo {
    public static void main(String args[])
    {

        // Calling the abstract
        // static method func()
        B.func();
        B b = new B();
        b.func1();
    }
}
```

**Output:** 

```java
Static method implemented.
Abstract method implemented.
```
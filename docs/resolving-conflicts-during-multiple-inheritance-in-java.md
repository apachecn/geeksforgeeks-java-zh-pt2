# 在 Java 中解决多重继承期间的冲突

> 原文:[https://www . geesforgeks . org/resolving-冲突-在 java 中多重继承期间/](https://www.geeksforgeeks.org/resolving-conflicts-during-multiple-inheritance-in-java/)

一个类可以在 java 中实现多个接口，但是如果实现的多个默认接口有相同签名的默认方法呢？然后在实现类中，从几个父接口调用哪个默认实现。

Java 8 设计人员一直在考虑这种冲突，并为这种场景指定了解决规则。现在让我们来看看潜在的冲突场景以及开发到 Java 8 中以避免冲突的解决规则。

继承的默认方法的冲突解决规则按优先级顺序如下

*   规则 1:类优先于接口
*   规则 2:派生接口或子接口比继承层次结构中更高层的接口具有更高的优先级
*   规则 3:如果规则 1 和规则 2 不能解决冲突，那么实现类必须专门重写并提供具有相同方法定义的方法。

现在让我们一个接一个地讨论它们，以获得对规则的内部工作流理解。

**实施:**

> **规则 1** 类优先于接口

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate
// classes take higher precedence than interfaces

// Importing input output classes
import java.io.*;

// Interface 1
interface A {
    public default void m1()
    {
        System.out.println("m1 method of interface m1");
    }
}

// Interface 2
interface B {
    public default void m1()
    {
        System.out.println("m1 method of interface B");
    }
}

// Helper class
class D {

    // Main driver method
    public void m1()
    {

        // Print statement when m1() of classD is called
        System.out.println("method of class D");
    }
}

// Main class
// It is implementing both the interfaces A and B
class C extends D implements A, B {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an object of this class
        // in the mai() method
        C c = new C();

        // Calling the method over the object created
        // to illustrate Classes take higher precedence
        // than interfaces
        c.m1();
    }
}
```

**输出:**

```
method of class D
```

输出解释:

由于 C 类从接口 A、接口 B 和超类 C 继承默认方法 m1()，如果 m1()方法在 C 类中被调用，那么超类 C 中的实现将被执行。

> **规则 2** 派生接口或子接口的优先级高于继承层次中更高的接口

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Derived interfaces or
// sub-interfaces take higher precedence than the interfaces
// higher-up in the inheritance hierarchy

// Interface 1
interface A {

    // Method of Interface 1
    public default void m1()
    {

        // Execution command whenever
        // interface 1 is called
        System.out.println("m1 method of A");
    }
}

// Interface 2
// This interface is extending above interface
interface B extends A {

    // Method of Interface 1
    public default void m1()
    {

        // Execution command whenever
        // interface 2 is called
        System.out.println("m1 method of B");
    }
}

// Main class
// Which is implementing Interface 2
class C implements B {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an object of this class
        // in the main method
        C c = new C();

        // Calling method over class object
        // created above to illustrate sub-interface
        // has higher precedence
        c.m1();
    }
}
```

**Output**

```
m1 method of B
```

输出解释:

因为接口 B 继承自接口 a。两者都有一个具有相同签名的默认方法 m1()。类 C 实现了接口 A 和 B。当在类 C 的实例上调用 m1()方法时，接口 B 中的实现被调用，因为它是继承层次结构中最低的子/最派生的接口。

> **规则 3** 如果规则 1 和规则 2 不能解决冲突，那么实现类必须专门覆盖并提供具有相同方法定义的方法

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to in which implementing class
// has to specifically override and provide a method
// with the same method definition
// to resolve the conflice

// Importing input output classes
import java.io.*;

// Interface 1
interface A {

    // m1() method of Interface 1/A
    public default void m1()
    {
        System.out.println("m1 method of interface m1");
    }
}

// Interface 2
interface B {

    // m1() method of Interface 2/B
    public default void m1()
    {
        System.out.println("m1 method of interface B");
    }
}

// Main Class
// This class implements both the interfaces
class C implements A, B {

    // Method 1
    // m1() method of class C (This class)
    public void m1()
    {

        // Super keyword called over m1() method
        // for interface 2/B
        B.super.m1();
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // Creating an object of this class
        // in the main() method
        C c = new C();

        // Calling the method 'm1()'
        // over the class object
        // in the main method()
        c.m1();
    }
}
```

**输出:**

```
m1 method of interface B
```

输出解释:

*   为了获得期望的行为，实现类当然可以从特定的父接口调用特定的默认方法。但是该类仍然需要重写默认方法来解决冲突并调用它。
*   C 类继承了上面例子中的 A & B 接口，所有这些接口都有默认的 m1()实现()。由于所有的 A & B 接口都是 C 的父接口，所以它们处于层次结构的同一级别，并且 C 还必须自己实现 m1()方法()。

> **注意:**在 print()方法的 C 类实现内部，它应该调用接口 A 或 b 的具体实现，为此 Java 8 有一个特殊的语法如下:
> 
> ```
> <super-interface-name>.super<method-name>
> ```
> 
> 在这种情况下，C 类中的 m1()方法将调用其父类 B 的 m1()方法，如下所示–B . super . m1()
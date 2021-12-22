# Java 中的包 vs 私有访问修饰符

> 原文:[https://www . geesforgeks . org/package-vs-private-access-modifiers-in-Java/](https://www.geeksforgeeks.org/package-vs-private-access-modifiers-in-java/)

每当我们编写类时，我们都必须向 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 提供一些关于我们的类的信息，比如这个类是否可以从任何地方访问，子类创建是否可能，对象创建是否可能等。我们可以通过在 java 中使用一个称为访问修饰符的适当关键字来指定这些信息。因此，访问修饰符用于设置类、方法和其他成员的可访问性。

让我们分别深入讨论这两个修饰语

*   包(默认)访问修饰符
*   私有访问修饰符

**修改器 1:** 包(默认)访问修改器

没有任何访问修饰符的类、方法或变量声明被认为具有包(默认)访问修饰符。默认修饰符在同一个包中充当公共的，在包外充当私有的。如果一个类被声明为默认类，那么我们只能在当前包中访问该类，也就是说，从外部包中我们不能访问它。因此，默认访问修饰符也被称为包级访问修饰符。类似的规则也适用于 java 中的变量和方法。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Package Level Access Modifier

// Importing utility classes
// Importing input output classes
import java.io.*;
import java.util.*;

// Main Class
class GFG {

    // Declaring default variables that is
    // having no access modifier
    String s = "Geeksfor";
    String s1 = "Geeks";

    // Method 1
    // To declare a default method
    String fullName()
    {
        // Concatenation of strings
        return s + s1;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of main class(GFG)
        // in the main() method
        GFG g = new GFG();

        // Calling method1 using class instance
        // and printing the concation of strings
        System.out.println(g.fullName());
    }
}
```

**输出:**

```java
GeeksforGeeks
```

**修饰符 2:** 私有访问修饰符

此修饰符不适用于顶级类或接口。它只适用于类内部的构造函数、方法和字段。如果一个变量、方法或构造函数被声明为私有的，那么我们只能从类内访问它们，也就是说，我们不能从类外访问它们。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to showcase Private Access Modifier

// Import required packages
import java.io.*;
import java.util.*;

// Class 1
// Helper class
class A {

    // Method
    private void m1()
    {

        // Print statement whenever the method is called
        System.out.println("GFG");
    }
}

// Class 2
// Main class
class B {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of type class A
        // in main() method
        A a = new A();

        // Now accessing the method m1() of
        // class created above
        a.m1();
    }
}
```

**输出:**

![](img/e19e9036578320fb0e5cb98efc1751d6.png)

最后，在完成这两者之后，让我们总结一下它们之间的明显差异，如下所示:

<figure class="table">

| **Package access modifier** | **Private access modifier** |
| --- | --- |
| This modifier applies to top-level classes and interfaces. | This modifier does not apply to top-level classes and interfaces. |
| Package members can be accessed from subclasses of the same package. | Private members cannot be accessed from subclasses of the same package. |
| Package members can be accessed from non-subclasses of the same package. | Private members cannot be accessed from non-subclasses of the same package. |
| Suit modifiers are more accessible than private modifiers. | Private modifiers are more restricted than suit modifiers. |
| Package modifier provides the lowest level of encapsulation in java. | A private modifier provides a higher level of encapsulation in Java. |

</figure>
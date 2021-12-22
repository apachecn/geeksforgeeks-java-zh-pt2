# Java 中的静态类

> 原文:[https://www.geeksforgeeks.org/static-class-in-java/](https://www.geeksforgeeks.org/static-class-in-java/)

**一个类在 Java 中可以是静态的吗？**
答案是肯定的，有些类可以用 Java 做静态的。Java 支持[静态实例变量](https://www.geeksforgeeks.org/static-keyword-in-java/)、[静态方法](https://www.geeksforgeeks.org/static-keyword-in-java/)、[静态块](https://www.geeksforgeeks.org/g-fact-79/)和静态类

Java 允许在另一个类中定义一个类。这些被称为**嵌套类**。定义嵌套类的类称为**外部类**。与顶级职业不同，**内部职业可以是静态的**。非静态嵌套类也称为**内部类**。

没有外部类的实例，就无法创建内部类的实例。因此，内部类实例可以访问其外部类的所有成员，而无需使用对外部类实例的引用。由于这个原因，内部类可以帮助程序变得简单和简洁。

**静态嵌套类和非静态嵌套类有什么区别？**
以下是静态嵌套类和内部类的主要区别。

1.  静态嵌套类可以在不实例化其外部类的情况下实例化。
2.  内部类可以访问外部类的静态和非静态成员。静态类只能访问外部类的静态成员。

```
// Java program to demonstrate how to
// implement static and non-static
// classes in a Java program.
class OuterClass {
    private static String msg = "GeeksForGeeks";

    // Static nested class
    public static class NestedStaticClass {

        // Only static members of Outer class
        // is directly accessible in nested
        // static class
        public void printMessage()
        {

            // Try making 'message' a non-static
            // variable, there will be compiler error
            System.out.println(
                "Message from nested static class: "
                + msg);
        }
    }

    // Non-static nested class -
    // also called Inner class
    public class InnerClass {

        // Both static and non-static members
        // of Outer class are accessible in
        // this Inner class
        public void display()
        {
            System.out.println(
                "Message from non-static nested class: "
                + msg);
        }
    }
}
class Main {
    // How to create instance of static
    // and non static nested class?
    public static void main(String args[])
    {

        // Create instance of nested Static class
        OuterClass.NestedStaticClass printer
            = new OuterClass.NestedStaticClass();

        // Call non static method of nested
        // static class
        printer.printMessage();

        // In order to create instance of
        // Inner class we need an Outer class
        // instance. Let us create Outer class
        // instance for creating
        // non-static nested class
        OuterClass outer = new OuterClass();
        OuterClass.InnerClass inner
            = outer.new InnerClass();

        // Calling non-static method of Inner class
        inner.display();

        // We can also combine above steps in one
        // step to create instance of Inner class
        OuterClass.InnerClass innerObject
            = new OuterClass().new InnerClass();

        // Similarly we can now call Inner class method
        innerObject.display();
    }
}
```

**输出:**

```
Message from nested static class: GeeksForGeeks
Message from non-static nested class: GeeksForGeeks
Message from non-static nested class: GeeksForGeeks
```

**参考书:**y . DANIEL LIANG 的《Java 编程入门》

本文由 **[钱德拉·普拉卡什](https://www.facebook.com/chandra.prakash.52643)** 供稿。如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论
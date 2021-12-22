# Java 中的变量不遵循多态性和覆盖

> 原文:[https://www . geesforgeks . org/variables-in-Java-do-not-follow-多态-override/](https://www.geeksforgeeks.org/variables-in-java-do-not-follow-polymorphism-and-overriding/)

Java 中的变量不遵循多态性。重写仅适用于方法，不适用于变量。在 Java 中，如果子类和父类都有一个同名的变量，子类的变量会隐藏父类的变量，即使它们的类型不同。这个概念被称为**变量隐藏**。在[方法覆盖](https://www.geeksforgeeks.org/overriding-in-java/)的情况下，覆盖方法完全替换继承的方法，但是在变量隐藏中，子类隐藏继承的变量而不是替换它们，这基本上意味着子类的对象包含两个变量，但是子类的变量隐藏父类的变量。

因此，当我们试图访问子类中的变量时，它将从子类中被访问。如果我们试图访问父类和子类之外的变量，那么从引用类型中选择实例变量。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating Instance variables
// Can not be Overridden

// Class 1
// Parent class
// Helper class
class Parent {
    // Declaring instance variable by name `a`
    int a = 10;
    public void print()
    {
        System.out.println("inside B superclass");
    }
}

// Class 2
// Child class
// Helper class
class Child extends Parent {

    // Hiding Parent class's variable `a` by defining a
    // variable in child class with same name.
    int a = 20;

    // Method defined inside child class
    public void print()
    {
        // Print statement
        System.out.println("inside C subclass");
    }
}

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Parent class object
        // Reference Parent
        Parent obj = new Child();

        // Calling print() method over object created
        obj.print();

        // Printing superclass variable value 10
        System.out.println(obj.a);

        // Creating a Child class object
        // Reference Child
        Child obj2 = new Child();

        // Printing childclass variable value 20
        System.out.println(obj2.a);
    }
}
```

**Output**

```
inside C subclass
10
20

```

> **结论:**
> 
> Java 中的变量不遵循多态性和重写。如果我们试图访问父类和子类之外的变量，那么从引用类型中选择实例变量。
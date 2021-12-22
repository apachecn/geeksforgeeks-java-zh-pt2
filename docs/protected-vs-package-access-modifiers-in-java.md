# Java 中受保护与包访问修饰符

> 原文:[https://www . geesforgeks . org/protected-vs-package-access-modifiers-in-Java/](https://www.geeksforgeeks.org/protected-vs-package-access-modifiers-in-java/)

每当我们编写类时，我们都必须向 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 提供一些关于我们的类的信息，比如这个类是否可以从任何地方访问，子类创建是否可能，对象创建是否可能等。我们可以通过在 java 中使用一个称为访问修饰符的适当关键字来指定这些信息。因此，访问修饰符用于设置类、方法和其他成员的可访问性。

**修饰符 1:** 受保护访问修饰符

此修饰符可以应用于数据成员、方法和构造函数，但不能应用于顶级类和接口。成员被声明为受保护的，因为我们只能在当前包中访问该成员，但只能在外部包的子类中访问。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to show Protected keyword

// Importing input output classes
import java.io.*;
// Importing utility classes
import java.util.*;

// Class 1
// Parent class
class Parent {

    // declaring a protected method m1()
    protected void print() { System.out.println("GFG"); }
}

// Class 2
// Child class which is extending Parent class
class Child extends Parent {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of parent class
        // using parent reference
        Parent p = new Parent();

        /// calling the print() method of Parent class
        p.print();

        // Creating an object of child class
        // using child reference
        Child c = new Child();

        // Calling the print() method of Parent class
        c.print();

        // Creating an object of child class
        // using parent reference
        Parent cp = new Child();

        // Calling the print method over this object
        cp.print();
    }
}
```

**Output**

```
GFG
GFG
GFG
```

**输出解释:**

在上面的例子中，我们使用父引用和子引用创建了三个对象，并在其上调用 m1()方法，它成功地执行了，因此从上面的例子中我们可以说，我们可以通过使用父引用或子引用在任何地方访问当前包中的受保护方法。

**修改器 2:** 包(默认)访问修改器

没有任何访问修饰符的类、方法或变量声明被认为具有包(默认)访问修饰符。默认修饰符在同一个包中充当公共的，在包外充当私有的。如果一个类被声明为默认类，那么我们只能在当前包中访问该类，也就是说，从外部包中我们不能访问它。因此，默认访问修饰符也被称为包**–**级访问修饰符。类似的规则也适用于 java 中的变量和方法。

**示例:**

## Java

```
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

**输出**

```
GeeksforGeeks
```

最后，在完成这两者之后，让我们总结一下它们之间的明显区别

<figure class="table">

| Package access modifier | Protected access modifier |
| --- | --- |
| This modifier is applicable to both top-level classes and interfaces | . This modifier is not applicable to top-level classes and interfaces |
| . We cannot access this modifier from subclasses of external packages. | We can access this modifier from subclasses of external packages, but we should only use sub-references. |
| This modifier is more restricted than the protected modifier. | This modifier is more accessible than the package modifier. |

</figure>
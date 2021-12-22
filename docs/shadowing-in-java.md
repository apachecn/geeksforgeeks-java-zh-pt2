# Java 中的阴影

> 原文:[https://www.geeksforgeeks.org/shadowing-in-java/](https://www.geeksforgeeks.org/shadowing-in-java/)

[内部类](https://www.geeksforgeeks.org/inner-class-java/)是指一个类是另一个类的成员。java 中基本上有四种类型的内部类。**嵌套内部类**可以访问外部类的任何私有实例变量。像任何其他实例变量一样，我们可以拥有访问修饰符 private、protected、public 和 default 修饰符。

Java 中的隐藏是在同名的重叠作用域中使用变量的实践，其中低级作用域中的变量覆盖高级作用域中的变量。这里，高级作用域的变量被低级作用域变量遮蔽。[基础知识这个关键词](https://www.geeksforgeeks.org/this-reference-in-java/)是前进前需要的。

**实施:**

在这里，我们将讨论几个例子来更好地理解这个概念，因为我们将能够更好地理解它和代码，稍后我们将讨论输出是如何生成的。

**例 1**

## Java

```
// Java program to Demonstrates Shadowing in Java

// Class 1 and 2
// Outer Class
class Shadowing {

    // Custom instance variable or member variable
    String name = "Outer John";

    // Nested inner class
    class innerShadowing {

        // Instance variable or member variable
        String name = "Inner John";

        // Method of this class to
        // print content of instance variable
        public void print()
        {

            // Print statements
            System.out.println(name);
            System.out.println(Shadowing.this.name);
        }
    }
}

// Class 3
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Accessing an inner class by
        // creating object of outer class inside main()
        Shadowing obj = new Shadowing();

        Shadowing.innerShadowing innerObj
            = obj.new innerShadowing();

        // Calling method defined inside inner class
        // inside main() method
        innerObj.print();
    }
}
```

**输出**

```
Inner John
Outer John
```

输出解释:

在这个例子中，你可以看到名字在**类以及 ***innerShadowing*** 类中被声明为 String 变量。当我们只打印名称时，它会打印存储在 ***【内阴影】*** 类中的名称值，因为这个类的范围小于外部类，所以它会覆盖名称的值。**

**让我们看另一个例子，它将更清楚地阐明这个概念，如下所示:**

****例 2****

**T5】JavaT0****T10**输出**T1

输出解释:

在本例中，我们将参数传递给 print()方法。所以我们现在可以看到，为了打印内部类的名称，我们需要使用“this”，因为 print()方法的作用域小于内部类的作用域，所以它也会覆盖内部类的名称。**
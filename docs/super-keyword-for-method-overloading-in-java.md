# Java 中方法重载的超级关键词

> 原文:[https://www . geesforgeks . org/super-keyword-for-method-overload-in-Java/](https://www.geeksforgeeks.org/super-keyword-for-method-overloading-in-java/)

我们使用 [**方法重载**](https://www.geeksforgeeks.org/overloading-in-java/) 来多次使用类似的方法。这可以通过在签名中使用不同的参数来实现。在下面的示例中，有一个具有三个类似方法的 GFG 类可用，尽管这三个方法是重载的，但它们具有不同的参数。GFG 类的对象调用一个带有字符串参数的方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the Method 
// Overloading without super keyword

class GFG {

    // Method m1 with 0 parameter.
    public void m1()
    {
        System.out.println("No parameter method");
    }

    // Method m1 with 1 integer parameter.
    public void m1(int i)
    {
        System.out.println("Int Parameter");
    }

    // Method m1 with 1 string parameter.
    public void m1(String s)
    {
        System.out.println("String Parameter");
    }
}

// Main Class
public class Main {

    public static void main(String[] args)
    {
        // Creating object for GFG class.
        // g is object of GFG class.
        GFG g = new GFG();

        // Here, m1 called with string parameter.
        // m1(String s) method will be called.
        g.m1("A");
    }
}
```

**输出:**

```
String Parameter

```

**使用** [**超**](https://www.geeksforgeeks.org/super-keyword/) **关键词:**

如果父类和子类具有相同的方法，那么子类将覆盖其父类中可用的方法。通过使用 super 关键字，我们可以利用两个类(子类和父类)来实现这一点。

*   我们创建一个子类的对象，因为它可以继承父类的方法。
*   在子类方法中，我们通过使用 super()调用其父类中可用的方法。

**注:**

在子类中，可以在任意行给出一个超级关键字。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GFG {

    // Method m1 with 0 parameter.
    public void m1()
    {
        System.out.println("No parameter method");
    }
}

// tech class extends class GFG
// Using Inheritance concept.
class tech extends GFG {

    // Method m1 with 0 parameter.
    public void m1()
    {
        System.out.println("Single Int Parameter");

        // Using super keyword to call
        // m1 method from class GFG.
        super.m1();
    }
}

// Main Class
public class Main {
    public static void main(String[] args)
    {
        // Creating object for tech class
        // obj is the object for tech class.
        tech obj = new tech();

        // tech class method m1
        // will be called here.
        // tech class extends GFG class

        // GFG class method m1 will be
        // called inside tech class method m1.

        // both method m1 will be called
        // one from tech class and
        // second from GFG class.
        obj.m1();
    }
}
```

**输出:**

```
Single Int Parameter
No parameter method

```

在下面的例子中，我们创建了一个继承了两个类 DP 和 CP 的编程对象。当使用 Programming 的对象调用方法 *learn* 时，它会转到自己的类 Programming，在它的类中我们有***super . learn()；*** 调用其父类的方法 super.learn()，现在在 CP 类中转到 ***super.learn()*** 后，再次调用其父类的 super.learn()，即来自 DP。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the use
// of super keyword with Method
// Overloading

class DP {
    // Class DP method learn
    // with 0 parameter.
    public void learn() { System.out.println("Dynamic"); }
}

// Class CP extends class DP
class CP extends DP {

    // Class CP method learn
    // with 0 parameter.
    public void learn()
    {
        // Using super keyword
        // here learn will be
        // called from class DP.
        super.learn();
        System.out.println("Competetive");
    }
}

// Class programming extends class
// CP that is extends class DP.
class Programming extends CP {

    // Class programming method
    // learn with 0 parameter.
    public void learn()
    {
        // Here, learn method from class CP
        // and learn method from class DP
        // which called inside class CP learn
        // method.
        super.learn();
        System.out.println("Programming");
    }
}

// Main Class
public class A {
    public static void main(String[] args)
    {
        // Creating object for class Programming.
        Programming obj = new Programming();
        // here, learn method will be called
        // from Programming class.

        // method will be also called
        // from programming class extends
        // class CP that is extends
        // class DP.
        obj.learn();
    }
}
```

**输出:**

```
Dynamic
Competetive
Programming

```
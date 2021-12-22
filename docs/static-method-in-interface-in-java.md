# Java 中接口的静态方法

> 原文:[https://www . geesforgeks . org/static-in-method-in-interface-in-Java/](https://www.geeksforgeeks.org/static-method-in-interface-in-java/)

**静态方法**界面**中的**是那些方法，在界面中用关键字 Static 定义。与接口中的其他方法不同，这些静态方法包含函数的完整定义，由于定义是完整的，并且方法是静态的，因此这些方法不能在实现类中被重写或更改。
类似于接口中的[默认方法，接口中的静态方法可以在接口中定义，但不能在实现类中覆盖。要使用静态方法，接口名称应该用它来实例化，因为它只是接口的一部分。
下面的程序说明了接口中的静态方法:
**程序 1:** 演示静态方法在接口中的使用。
在这个程序中，一个简单的静态方法是在一个接口中定义和声明的，这个接口在实现类 InterfaceDemo 的 main()方法中被调用。与默认方法不同，在接口 hello()中定义的静态方法不能在实现类时被重写。](https://www.geeksforgeeks.org/default-methods-java/) 

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// static method in Interface.

interface NewInterface {

    // static method
    static void hello()
    {
        System.out.println("Hello, New Static Method Here");
    }

    // Public and abstract method of Interface
    void overrideMethod(String str);
}

// Implementation Class
public class InterfaceDemo implements NewInterface {

    public static void main(String[] args)
    {
        InterfaceDemo interfaceDemo = new InterfaceDemo();

        // Calling the static method of interface
        NewInterface.hello();

        // Calling the abstract method of interface
        interfaceDemo.overrideMethod("Hello, Override Method here");
    }

    // Implementing interface method

    @Override
    public void overrideMethod(String str)
    {
        System.out.println(str);
    }
}
```

**Output:** 

```java
Hello, New Static Method Here
Hello, Override Method here
```

**程序 2:** 演示静态方法的范围。
在这个程序中，静态方法定义的范围仅在接口内。如果在实现类中实现了同名方法，那么该方法将成为相应类的静态成员。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate scope
// of static method in Interface.

interface PrintDemo {

    // Static Method
    static void hello()
    {
        System.out.println("Called from Interface PrintDemo");
    }
}

public class InterfaceDemo implements PrintDemo {

    public static void main(String[] args)
    {

        // Call Interface method as Interface
        // name is preceding with method
        PrintDemo.hello();

        // Call Class static method
        hello();
    }

    // Class Static method is defined
    static void hello()
    {
        System.out.println("Called from Class");
    }
}
```

**Output:** 

```java
Called from Interface PrintDemo
Called from Class
```
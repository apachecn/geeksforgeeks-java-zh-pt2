# Java 9 接口中的私有方法

> 原文:[https://www . geesforgeks . org/private-methods-Java-9-interfaces/](https://www.geeksforgeeks.org/private-methods-java-9-interfaces/)

从 Java 9 开始，您可以在接口中包含私有方法。在 Java 9 之前，这是不可能的。

【Java 7 之前的接口

在 Java SE 7 或更早的版本中，一个接口只能有两样东西，即**常量变量和**抽象方法。这些接口方法必须由选择实现接口的类来实现。

```java
// Java 7 program to illustrate
// private methods in interfaces
public interface TempI {
    public abstract void method(int n);
}

class Temp implements TempI {
    @Override
    public void method(int n)
    {
        if (n % 2 == 0)
            System.out.println("geeksforgeeks");
        else
            System.out.println("GEEKSFORGEEKS");
    }

    public static void main(String[] args)
    {
        TempI in1 = new Temp();
        TempI in2 = new Temp();
        in1.method(4);
        in2.method(3);
    }
}
```

```java
OUTPUT : geeksforgeeks
         GEEKSFORGEEKS

```

**Java 8 界面更改**

Java 8 中引入了一些新的接口特性，即默认方法和静态方法特性。在 Java 8 中，一个接口只能有四种类型:

1.  常量变量
2.  抽象方法
3.  默认方法
4.  静态方法

**例**

```java
// Java 8 program to illustrate
// static, default and abstract methods in interfaces
public interface TempI {

    public abstract void div(int a, int b);

public default void
    add(int a, int b)
    {
        System.out.print("Answer by Default method = ");
        System.out.println(a + b);
    }

    public static void mul(int a, int b)
    {
        System.out.print("Answer by Static method = ");
        System.out.println(a * b);
    }
}

class Temp implements TempI {

    @Override
    public void div(int a, int b)
    {
        System.out.print("Answer by Abstract method = ");
        System.out.println(a / b);
    }

    public static void main(String[] args)
    {
        TempI in = new Temp();
        in.div(8, 2);
        in.add(3, 1);
        TempI.mul(4, 1);
    }
}
```

```java
OUTPUT : Answer by Abstract method = 4
         Answer by Default method = 4
         Answer by Static method = 4

```

**Java 9 界面更改**

Java 9 在接口中引入了私有方法和私有静态方法。在 Java 9 和更高版本中，一个接口可以有六种不同的东西:

1.  常量变量
2.  抽象方法
3.  默认方法
4.  静态方法
5.  私有方法
6.  Private Static methods

    这些私有方法将提高接口内部代码的可重用性，并将提供仅向用户公开我们的预期方法实现的选择。这些方法只能在该接口内访问，不能从一个接口访问或继承到另一个接口或类。

    ```java
    // Java 9 program to illustrate
    // private methods in interfaces
    public interface TempI {

        public abstract void mul(int a, int b);

    public default void
        add(int a, int b)
        {
    // private method inside default method
            sub(a, b); 

     // static method inside other non-static method
            div(a, b);
            System.out.print("Answer by Default method = ");
            System.out.println(a + b);
        }

        public static void mod(int a, int b)
        {
            div(a, b); // static method inside other static method
            System.out.print("Answer by Static method = ");
            System.out.println(a % b);
        }

        private void sub(int a, int b)
        {
            System.out.print("Answer by Private method = ");
            System.out.println(a - b);
        }

        private static void div(int a, int b)
        {
            System.out.print("Answer by Private static method = ");
            System.out.println(a / b);
        }
    }

    class Temp implements TempI {

        @Override
        public void mul(int a, int b)
        {
            System.out.print("Answer by Abstract method = ");
            System.out.println(a * b);
        }

        public static void main(String[] args)
        {
            TempI in = new Temp();
            in.mul(2, 3);
            in.add(6, 2);
            TempI.mod(5, 3);
        }
    }
    ```

    ```java
    OUTPUT : Answer by Abstract method = 6              // mul(2, 3) = 2*3 = 6
             Answer by Private method = 4               // sub(6, 2) = 6-2 = 4 
             Answer by Private static method = 3        // div(6, 2) = 6/2 = 3
             Answer by Default method = 8               // add(6, 2) = 6+2 = 8
             Answer by Private static method = 1        // div(5, 3) = 5/3 = 1 
             Answer by Static method = 2                // mod(5, 3) = 5%3 = 2

    ```

    **在接口中使用私有方法的规则**

    *   私有接口方法不能是抽象的，并且不能同时有私有和抽象修饰符。
    *   私有方法只能在接口内部以及其他静态和非静态接口方法中使用。
    *   私有非静态方法不能在私有静态方法中使用。
    *   我们应该使用私有修饰符来定义这些方法，并且不低于私有修饰符的可访问性。

    所以，从上面可以看出，java 9 私有接口方法可以是静态的，也可以是实例的。在这两种情况下，子接口或实现都不会继承私有方法。它们主要是为了提高代码在接口内的可重用性，从而提高封装性。
# Java 中的静态变量，示例

> 原文:[https://www . geesforgeks . org/static-variables-in-Java-with-examples/](https://www.geeksforgeeks.org/static-variables-in-java-with-examples/)

当一个变量被声明为[静态](https://www.geeksforgeeks.org/static-keyword-java/)时，该变量的单个副本被创建并在类级别的所有对象之间共享。静态变量本质上是全局变量。该类的所有实例共享同一个静态变量。

**静态变量的要点:**

*   We can only create static variables at the class level. See here.
*   Static blocks and static variables are executed in the order in which they appear in the program.

下面是 java 程序，演示了静态块和静态变量是按照它们在程序中出现的顺序执行的。

```java
// Java program to demonstrate execution
// of static blocks and variables

class Test {

    // static variable
    static int a = m1();

    // static block
    static
    {
        System.out.println("Inside static block");
    }

    // static method
    static int m1()
    {
        System.out.println("from m1");
        return 20;
    }

    // static method(main !!)
    public static void main(String[] args)
    {
        System.out.println("Value of a : " + a);
        System.out.println("from main");
    }
}
```

**输出:**

```java
from m1
Inside static block
Value of a : 20
from main

```
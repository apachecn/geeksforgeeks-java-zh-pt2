# Java 中的静态导入

> 原文:[https://www.geeksforgeeks.org/static-import-java/](https://www.geeksforgeeks.org/static-import-java/)

在 Java 中，1.5 版本引入了静态导入的概念。借助静态导入，我们可以直接访问类的静态成员，而不需要类名或任何对象。例如:我们总是通过使用 Math 类来使用 Math 类的 sqrt()方法，即 **Math.sqrt()** ，但是通过使用静态导入我们可以直接访问 sqrt()方法。
根据 SUN 微系统的说法，它将提高代码可读性，增强编码。但是按照编程专家的说法，会导致混乱，不利于编程。如果没有具体要求，那么我们应该**而不是**去做静态导入。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java Program to illustrate
// calling of predefined methods
// without static import
class Geeks {
    public static void main(String[] args)
    {
        System.out.println(Math.sqrt(4));
        System.out.println(Math.pow(2, 2));
        System.out.println(Math.abs(6.3));
    }
}
```

**输出:**

```
2.0
4.0
6.3 
```

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java Program to illustrate
// calling of predefined methods
// with static import
import static java.lang.Math.*;
class Test2 {
    public static void main(String[] args)
    {
        System.out.println(sqrt(4));
        System.out.println(pow(2, 2));
        System.out.println(abs(6.3));
    }
}
```

**输出:**

```
2.0
4.0
6.3
```

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java to illustrate calling of static member of
// System class without Class name
import static java.lang.Math.*;
import static java.lang.System.*;
class Geeks {
    public static void main(String[] args)
    {
        // We are calling static member of System class
        // directly without System class name
        out.println(sqrt(4));
        out.println(pow(2, 2));
        out.println(abs(6.3));
    }
}
```

**输出:**

```
2.0
4.0
6.3
```

**注意:** System 是 java.lang 包中存在的类，out 是 System 类中存在的静态变量。借助静态导入，我们可以在没有类名的情况下调用它。

**静态导入中的歧义:**
如果从多个不同的类中导入两个同名的静态成员，编译器会抛出一个错误，因为在没有类名限定的情况下，它将无法确定使用哪个成员。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate
// ambiguity in case of
// static import
import static java.lang.Integer.*;
import static java.lang.Byte.*;
class Geeks {
    public static void main(String[] args)
    {
        out.println(MAX_VALUE);
    }
}
```

**输出:**

```
Error:Reference to MAX_VALUE is ambigious
```

**解释:**在上面的程序中，我们试图访问 MAX_VALUE 变量，但是每个原语数据类型都包含 MAX_VALUE 变量，该变量在 Wrapper 类中预先声明。这里我们同时导入整数和字节类，并试图访问静态变量 MAX_VALUE，但是这里编译器会因为看到两个导入语句而感到困惑，因为整数和字节类都包含一个静态变量 MAX_VALUE。因此这里编译器抛出一个错误说**对 MAX_VALUE 的引用是有界限的**。
**注:**两个包包含两个同名的类/接口非常少见。因此，我们很少会在以正常方式导入时出现任何歧义，即正常导入。但是两个类可能包含相同的变量，因此在静态导入中经常会出现引用不明确的错误。这就是为什么如果没有这样的要求，不建议使用。

**导入与静态导入的区别:**

*   在导入的帮助下，我们能够访问任何包中存在的类和接口。但是使用静态导入，我们可以直接访问一个类的所有静态成员(变量和方法)，而无需显式调用类名。
*   主要区别是可读性，与数据成员(out)相比，class name . dataMember(system . out)的可读性较差，静态导入可以使您的程序更具可读性
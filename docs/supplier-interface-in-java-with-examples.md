# Java 供应商界面，示例

> 原文:[https://www . geesforgeks . org/supplier-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/)

**供应商界面**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[功能编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个不接受任何参数但产生一个类型为 t 的值的函数

因此，该功能界面只接受一个类属，即:-

*   **: indicates the type of result.**

**分配给供应商类型的对象的 lambda 表达式用于定义其 **get()** ，最终产生一个值。当我们不需要同时提供任何价值和获得结果时，供应商是有用的。**

**供应商界面仅包含一个功能:**

### **1.get()**

**这个方法不接受任何参数，但是产生一个类型为 t 的值**

****语法:****

```java
T get()
```

****返回:**该方法返回一个类型为 T 的**值****

**下面是说明 get()方法的代码:**

****程序:****

```java
import java.util.function.Supplier;

public class Main {
    public static void main(String args[])
    {

        // This function returns a random value.
        Supplier<Double> randomValue = () -> Math.random();

        // Print the random value using get()
        System.out.println(randomValue.get());
    }
}
```

****输出:**

```java
0.5685808855697841

```**
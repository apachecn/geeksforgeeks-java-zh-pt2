# 用示例将 Java 中的函数接口翻倍

> 原文:[https://www . geesforgeks . org/to doublefunction-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/todoublefunction-interface-in-java-with-examples/)

**到双功能接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[功能编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个函数，该函数接受类型为 **T** 的参数并产生一个双值结果。

该功能界面只接受一个泛型，即:-

*   **: indicates the type of input parameter of the operation.**

**分配给 ToDoubleFunction 类型的对象的 lambda 表达式用于定义其 **applyAsDouble()** ，该表达式最终对其唯一的参数应用给定的操作。这类似于使用类型为[功能](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/) < T，双>的对象。**

**ToDoubleFunction 接口只有一个功能:**

### **applyAsDouble()**

**此方法接受一个类型为 T 的参数，并给出一个双值结果。**

****语法:****

```
double applyAsDouble(T value)
```

****参数:**该方法取一个参数**值**，为 t 型自变量**

****返回:**该方法返回一个**双值**结果。**

**下面是演示 applyAsDouble()方法的代码:**

****程序****

```
import java.util.function.ToDoubleFunction;

public class Main {
    public static void main(String args[])
    {
        ToDoubleFunction<Integer> ob = a -> a / 2;

        // using applyAsDouble()
        System.out.println(ob.applyAsDouble(3));
    }
}
```

****输出:**

```
1.0

```**
# 用示例在 Java 中调用函数接口

> 原文:[https://www . geesforgeks . org/to intfunction-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/tointfunction-interface-in-java-with-examples/)

**到函数接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个函数，该函数接受类型为 **T** 的参数并产生一个整型值的结果。

该功能界面只接受一个泛型，即:-

*   **: indicates the type of input parameter of the operation.**

**分配给 ToIntFunction 类型的对象的 lambda 表达式用于定义其 **applyAsInt()** ，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为[函数](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/) < T，整数>的对象。**

**ToIntFunction 接口只有一个功能:**

### **applyAsInt()**

**这个方法接受一个类型为 T 的参数，并给出一个整型值的结果。**

****语法:****

```
int applyAsInt(T value)
```

****参数:**该方法取一个参数**值**，为 t 型自变量**

****返回:**该方法返回一个**整数值**结果。**

**下面是说明 applyAsInt()方法的代码:**

****程序****

```
import java.util.function.ToIntFunction;

public class Main {
    public static void main(String args[])
    {

        // Instantiating ToIntFunction
        ToIntFunction<Double> ob = a -> (int)(a * 10);

        // Applying the above function
        // using applyAsInt()
        System.out.println(ob.applyAsInt(3.2));
    }
}
```

****输出:**

```
32

```**
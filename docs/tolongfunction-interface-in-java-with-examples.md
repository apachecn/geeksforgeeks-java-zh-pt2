# 用示例展示 Java 中的函数接口

> 原文:[https://www . geesforgeks . org/tolongfunction-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/tolongfunction-interface-in-java-with-examples/)

**ToLongFunction 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受类型为 **T** 的参数并产生长值结果的函数。

该功能界面只接受一个泛型，即:-

*   **: indicates the type of input parameter of the operation.**

**分配给 ToLongFunction 类型的对象的 lambda 表达式用于定义其 **applyAsLong()** ，该表达式最终对其唯一的参数应用给定的操作。类似于使用[函数](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/) < T，龙>类型的对象。**

**ToLongFunction 接口只有一个功能:**

### **applyAsLong():**

**这个方法接受一个类型为 T 的参数，并给出一个长值结果。**

****语法:****

```
long applyAsLong(T value)
```

****参数:**该方法取一个参数**值**，为 t 型自变量**

****返回:**该方法返回一个**长值**结果。**

**下面是说明 applyAsLong()方法的代码:**

****程序****

```
import java.util.function.ToLongFunction;

public class Main {
    public static void main(String args[])
    {

        // Instantiating ToLongFunction
        ToLongFunction<Integer> ob = a -> a * 10000;

        // Applying the above function
        // using applyAsLong()
        System.out.println(ob.applyAsLong(3));
    }
}
```

****输出:**

```
30000

```**
# Java 中的无操作界面

> 原文:[https://www . geesforgeks . org/unaryooperator-interface-in-Java/](https://www.geeksforgeeks.org/unaryoperator-interface-in-java/)

**一元运算符接口< T >** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程。](https://www.geeksforgeeks.org/functional-programming-paradigm/)表示接受一个参数并对其进行运算的函数。然而，它与普通函数的区别在于它的参数和返回类型是相同的。

因此，该功能界面采用一个通用名称，即:-

*   **: indicates the type of input parameter of the operation.**

**因此，一元运算符<t>重载函数<t t="">类型。所以从功能界面继承了以下方法:</t></t>**

*   **[T 敷(T)](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/)**
*   **[Default < V > Function < T, V > Then (Function < Super r,? After extending V >)](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/)**
***   [Default < V > Function < V, R > Composition (Function < Super v,? Before extending t >)](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/)**

**分配给 UnaryOperator 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终对其参数应用给定的操作。**

### **一元运算符接口中的函数**

**一元运算符接口由以下功能组成:**

### **1.身份()**

**这个方法返回一个 UnaryOperator，它接受一个值并返回它。返回的 UnaryOperator 不对其唯一值执行任何操作。**

****语法:****

```java
static  UnaryOperator identity()
```

****参数:**该方法不取任何参数。**

****返回:**取一个值并返回的一元运算符。**

**下面是说明 accept()方法的代码:**

****程序 1:****

```java
import java.util.function.UnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        // Instantiate the UnaryOperator interface
        UnaryOperator<Boolean>
            op = UnaryOperator.identity();

        // Apply identify() method
        System.out.println(op.apply(true));
    }
}
```

****输出:**

```java
true

```**
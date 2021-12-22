# Java 中的舍入误差

> 原文:[https://www.geeksforgeeks.org/rounding-off-errors-java/](https://www.geeksforgeeks.org/rounding-off-errors-java/)

将许多无限实数压缩成有限位数需要一个近似表示。大多数程序最多存储 32 或 64 位的整数计算结果。给定任何固定的位数，大多数实数计算将产生无法用这么多位精确表示的量。因此，浮点计算的结果必须经常进行舍入，以适应其有限的表示形式。这种舍入误差是浮点计算的一个特征。

因此，在处理浮点数计算时(尤其是如果计算是以金钱为单位)，我们需要注意编程语言中的舍入误差。
我们来看一个例子:

```
public class Main {
    public static void main(String[] args)
    {
        double a = 0.7;
        double b = 0.9;
        double x = a + 0.1;
        double y = b - 0.1;

        System.out.println("x = " + x);
        System.out.println("y = " + y );
        System.out.println(x == y);
    }
}
```

输出:

```
x = 0.7999999999999999
y = 0.8
false

```

这里，答案不是我们所期望的原因，而是 java 编译器所做的舍入。

 **舍入误差背后的原因**

浮点和双数据类型实现 IEEE 浮点 754 规范。这意味着数字以如下形式表示:

```
SIGN FRACTION * 2 ^ EXP 
```

0.15625 = (0.00101) <sub>2</sub> ，在浮点格式中表示为:1.01 * 2^-3
并不是所有的分数都能精确表示为 2 的幂的分数。举个简单的例子，0.1 =(0.0001100110011001100110011001100110011001100110011001100110011001……)<sub>2</sub>因此不能存储在浮点变量中。

另一个例子:

```
public class Main {
    public static void main(String[] args)
    {
        double a = 0.7;
        double b = 0.9;
        double x = a + 0.1;
        double y = b - 0.1;

        System.out.println("x = " + x);
        System.out.println("y = " + y );
        System.out.println(x == y);
    }
}
```

输出:

```
x = 0.7999999999999999
y = 0.8
false

```

另一个例子:

```
public class Main {
    public static void main(String args[])
    {
        double a = 1.0;
        double b = 0.10;
        double x = 9 * b;
        a = a - (x);

        // Value of a is expected as 0.1
        System.out.println("a = " + a);
    }
}
```

输出:

```
a = 0.09999999999999998

```

**如何纠正舍入误差？** 

*   **舍入结果:**Round()函数可用于最小化浮点算术存储不精确的任何影响。用户可以将数字四舍五入到计算所需的小数位数。例如，在使用货币时，您可能会四舍五入到小数点后两位。
*   **算法和函数:**使用数值稳定的算法或设计自己的函数来处理这种情况。您可以截断/舍入您不确定是否正确的数字(您也可以计算运算的数值精度)
*   **BigDecimal Class:** You may use the [java.math.BigDecimal](http://docs.oracle.com/javase/1.5.0/docs/api/java/math/BigDecimal.html) class, which is designed to give us accuracy especially in case of big fractional numbers.

    以下程序显示了如何消除错误:

    ```
    public class Main {
        public static void main(String args[])
        {
            double a = 1.0;
            double b = 0.10;
            double x = 9 * b;
            a = a - (x);

        /* We use Math.round() function to round the answer to
             closest long, then we multiply and divide by 1.0 to
             to set the decimal places to 1 place (this can be done
             according to the requirements.*/
            System.out.println("a = " + Math.round(a*1.0)/1.0);
        }
    }
    ```

    输出:

    ```
    0.1
    ```

    现在我们得到了预期的输出，没有错误。

    如果你喜欢 GeeksforGeeks 并且愿意投稿，你也可以使用[contribute.geeksforgeeks.org](https://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
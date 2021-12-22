# Java 中的 Period 乘()方法，示例

> 原文:[https://www . geesforgeks . org/period-by-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-multipliedby-method-in-java-with-examples/)

Java 中 Period 类的 **multipliedBy()** 方法用于从给定的周期中乘上周期 YEAR，MONTH，DAY 的每个元素后，返回 Period 的一个新实例。该功能仅适用于所有三个年份、月份和日期。

**语法:**

```java
public Period multipliedBy(int toMultiply)
```

**参数:**此方法接受单个参数*乘以*，这是要乘以周期的标量数。

**返回值:**此方法在将周期的每个元素乘以给定的倍数输入后，返回周期的新实例。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

以下是上述方法的实现:
**程序一**:

```java
// Java code to show the function multipliedBy()
// to multiply the given number to given period

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to multiply a constant to given periods
    static void multiply(Period p1, int toMultiply)
    {
        System.out.println(p1.multipliedBy(toMultiply));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        int toMultiply = 2;

        multiply(p1, toMultiply);
    }
}
```

**程序 2** :

```java
// Java code to show the function multipliedBy()
// to multiply the given number to given period

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to multiply a constant to given periods
    static void multiply(Period p1, int toMultiply)
    {
        System.out.println(p1.multipliedBy(toMultiply));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = -4;
        int months = -11;
        int days = -10;
        Period p1 = Period.of(year, months, days);

        int toMultiply = 2;

        multiply(p1, toMultiply);
    }
}
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html #乘法 By-int-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#multipliedBy-int-)
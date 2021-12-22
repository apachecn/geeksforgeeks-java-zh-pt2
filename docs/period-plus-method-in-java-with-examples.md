# Java 中的 Period plus()方法，示例

> 原文:[https://www . geesforgeks . org/period-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-plus-method-in-java-with-examples/)

Java 中 Period 类的 plus()方法用于将给定数量的周期添加到指定的周期中。该功能在年、月和日分别运行。

**注意:**不进行归一化。12 个月和 1 年是不同的。

**语法:**

```
public Period plus(TemporalAmount amountToAdd)
```

**参数:**此功能接受单个参数*金额添加*，即**金额**添加至期间。它不能为空。

**返回值**该函数根据给定的周期返回一个周期，加上请求的周期，该值不能为空。

**例外:**

*   **Date and time exception** : If the specified amount has a non-ISO chronology or contains invalid units, this exception will be returned.
*   **Arithmetic exception** : If there is a numerical overflow, catch the exception.

下面的程序说明了上述方法:

**程序 1** :

```
// Java code to show the function plus()
// to subtract the two given periods

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to subtract two given periods
    static void addPeriod(Period p1, Period p2)
    {

        System.out.println(p1.plus(p2));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        // Defining second period
        int year1 = 2;
        int months1 = 7;
        int days1 = 8;
        Period p2 = Period.of(year1, months1, days1);

        addPeriod(p1, p2);
    }
}
```

**输出:**

```
P6Y18M18D

```

**程序二**:期间可以为负数。

```
// Java code to show the function plus()
// to subtract the two given periods

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to add two given periods
    static void addPeriod(Period p1, Period p2)
    {

        System.out.println(p1.plus(p2));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining second period
        int year1 = 2;
        int months1 = 7;
        int days1 = 8;
        Period p1 = Period.of(year1, months1, days1);

        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p2 = Period.of(year, months, days);

        addPeriod(p1, p2);
    }
}
```

**输出:**

```
P6Y18M18D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # plus-Java . time . temporal mount-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#plus-java.time.temporal.TemporalAmount-)
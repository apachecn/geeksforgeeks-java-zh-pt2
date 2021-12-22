# Java 中的 Period 减()方法，示例

> 原文:[https://www . geeksforgeeks . org/period-减去-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-minus-method-in-java-with-examples/)

Java 中 Period 类的减()方法用于从指定的周期中减去给定的周期量。该功能在年、月和日分别运行。

**注意:**不进行归一化。12 个月和 1 年是不同的。

**语法:**

```
public Period minus(TemporalAmount amountToSubtract)
```

**参数:**该方法接受单个参数 *amountToSubtract* ，即从该周期减去的**量**。它不能为空。

**返回值:**该方法根据给定的周期，减去请求的周期，返回一个周期，该值不能为空。

**例外:**

*   **Date and time exception** : If the specified amount has a non-ISO chronology or contains invalid units, this exception will be returned.
*   **Arithmetic exception** : If there is a numerical overflow, catch the exception.

下面的程序说明了上述方法:

**程序 1** :

```
// Java code to show the function minus()
// to subtract the two given periods
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to subtract two given periods
    static void subtractPeriod(Period p1, Period p2)
    {

        System.out.println(p1.minus(p2));
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

        subtractPeriod(p1, p2);
    }
}
```

**输出:**

```
P2Y4M2D

```

**程序二** :

```
// Java code to show the function minus()
// to subtract the two given periods
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to subtract two given periods
    static void subtractPeriod(Period p1, Period p2)
    {

        System.out.println(p1.minus(p2));
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

        subtractPeriod(p1, p2);
    }
}
```

**输出:**

```
P-2Y-4M-2D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html #减-Java . time . temporal mount-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#minus-java.time.temporal.TemporalAmount-)
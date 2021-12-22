# Java 中的 Period minusMonths()方法，带示例

> 原文:[https://www . geesforgeks . org/period-MINUS 月-java 中的方法-示例/](https://www.geeksforgeeks.org/period-minusmonths-method-in-java-with-examples/)

Java 中 Period 类的 minusMonths()方法用于从给定的周期中减去指定的月份。这种方法只在月份运行，不影响其他两个年份。

**语法:**

```
public Period minusMonths(long monthsToSubtract)
```

**参数:**该方法接受单个参数*月至月*，即从周期中减去的月数。

**返回值:**此方法根据输入中提供的期间减去指定的月数返回一个期间。它不能为空。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上述方法:

**程序 1** :

```
// Java code to show the function minusMonths()
// to subtract the number of months from given periods

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to subtract two given periods
    static void subtractMonths(Period p1, int monthstoSubtract)
    {
        System.out.println(p1.minusMonths(monthstoSubtract));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        int monthstoSubtract = 8;

        subtractMonths(p1, monthstoSubtract);
    }
}
```

**输出:**

```
P4Y3M10D

```

**程序二** :

```
// Java code to show the function minusMonths()
// to subtract the number of months from given periods

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to subtract two given periods
    static void subtractMonths(Period p1, int monthstoSubtract)
    {
        System.out.println(p1.minusMonths(monthstoSubtract));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = -4;
        int months = -11;
        int days = -10;
        Period p1 = Period.of(year, months, days);

        int monthstoSubtract = -8;

        subtractMonths(p1, monthstoSubtract);
    }
}
```

**输出:**

```
P-4Y-3M-10D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html #不稳定月长-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#minusMonths-long-)
# Java 中的 Period distants()方法，带示例

> 原文:[https://www . geeksforgeeks . org/period-mins days-in-Java-method-with-examples/](https://www.geeksforgeeks.org/period-minusdays-method-in-java-with-examples/)

Java 中 Period 类的 minusDays()方法用于从这个 Period 中减去天数。该功能仅在工作日运行，不影响年和月。

**语法:**

```java
public Period minusDays(long daysToSubtract)
```

**参数:**该方法接受单个参数*天数减去*，即从周期中减去的天数。

**返回值:**该方法根据输入
中提供的期间减去指定天数返回一个期间。它不能为空。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上述方法:

**程序 1** :

```java
// Java code to show the function minusDays()
// to subtract the number of days from given periods

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to subtract two given periods
    static void subtractDays(Period p1, int daystoSubtract)
    {

        System.out.println(p1.minusDays(daystoSubtract));
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        int daystoSubtract = 8;

        subtractDays(p1, daystoSubtract);
    }
}
```

**Output:**

```java
P4Y11M2D

```

**程序 2** :

```java
// Java code to show the function minusDays()
// to subtract the number of days from given periods
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to subtract two given periods
    static void subtractDays(Period p1, int daystoSubtract)
    {

        System.out.println(p1.minusDays(daystoSubtract));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = -4;
        int months = -11;
        int days = 0;
        Period p1 = Period.of(year, months, days);

        int daystoSubtract = 8;

        subtractDays(p1, daystoSubtract);
    }
}
```

**Output:**

```java
P-4Y-11M-8D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html #不稳定天数-长-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#minusDays-long-)
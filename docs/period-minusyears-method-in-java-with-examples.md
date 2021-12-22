# Java 中的 Period minusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/period-mins years-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-minusyears-method-in-java-with-examples/)

Java 中 Period 类的 **minusYears()** 方法用于从给定的周期中减去指定的年份。该功能仅在年运行，不影响其他两个月和天。

**语法:**

```java
public Period minusYears(long yearsToSubtract)
```

**参数:**该方法接受单个参数 *yearsToSubtract* ，即从周期中减去的年数。

**返回值**:该方法根据输入中提供的期间减去指定的年数返回一个期间。它不能为空。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上述方法:

**程序 1** :

```java
// Java code to show the function minusYears()
// to subtract the number of years from given period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to subtract two given periods
    static void subtractYears(Period p1, int yearstoSubtract)
    {

        System.out.println(p1.minusYears(yearstoSubtract));
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        int yearstoSubtract = 8;

        subtractYears(p1, yearstoSubtract);
    }
}
```

**输出:**

```java
P-4Y11M10D

```

**程序二** :

```java
// Java code to show the function minusYears()
// to subtract the number of years from given period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to subtract two given periods
    static void subtractYears(Period p1, int yearstoSubtract)
    {

        System.out.println(p1.minusYears(yearstoSubtract));
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        int yearstoSubtract = -8;

        subtractYears(p1, yearstoSubtract);
    }
}
```

**输出:**

```java
P12Y11M10D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html #不稳定年长-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#minusYears-long-)
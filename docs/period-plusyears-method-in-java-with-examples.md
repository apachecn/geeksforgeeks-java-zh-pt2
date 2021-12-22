# Java 中的 Period plusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/period-plusyears-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-plusyears-method-in-java-with-examples/)

Java 中 Period 类的 plusYears()方法用于将给定的年份添加到此期间。该功能仅在年运行，不影响月和日。

**语法:**

```
public Period plusYears(long yearsToAdd)
```

**参数:**此方法接受单个参数*年数添加*，即要添加到周期中的年数。

**返回值:**该方法根据输入中提供的期间，加上指定的年数，返回一个期间。它不能为空。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上述方法:

**程序 1:**

```
// Java code to show the function plusYears()
// to add the number of years from given periods
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to add years to given period
    static void addYears(Period p1, int yearstoAdd)
    {

        System.out.println(p1.plusYears(yearstoAdd));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        int yearstoAdd = 8;

        addYears(p1, yearstoAdd);
    }
}
```

**输出:**

```
P12Y11M10D

```

**程序二**:期间可以为负数。

```
// Java code to show the function plusYears()
// to add the number of years to given periods
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to add years to given periods
    static void addYears(Period p1, int yearstoAdd)
    {

        System.out.println(p1.plusYears(yearstoAdd));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = -4;
        int months = -11;
        int days = 0;
        Period p1 = Period.of(year, months, days);

        int yearstoAdd = 8;

        addYears(p1, yearstoAdd);
    }
}
```

**输出:**

```
P4Y-11M

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # plusYears-long-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#plusYears-long-)
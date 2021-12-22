# Java 中()方法之间的周期，示例

> 原文:[https://www . geesforgeks . org/period-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-between-method-in-java-with-examples/)

Java 中 Period 类的 between()方法用于获取由两个给定日期(包括开始日期和不包括结束日期)之间的年数、月数和天数组成的期间。

该期间的获取方式如下:

*   Remove the whole month.
*   Now, calculate the remaining days.
*   Then, make adjustments to ensure that both have the same logo.
*   Now, the number of months is divided into years and months according to the year of 12 months.
*   Consider one month, if the end of the month is greater than or equal to the beginning of the month (for example, from May 12, 2017 to July 18, 2018 is one year, two months and six days).

**注意:**由上述公式得到的周期，如果结束在开始之前，可以是一个*负数*。负号在每年、每月和每一天都是一样的。

**语法:**

```
public static Period between(LocalDate startDateInclusive,
                             LocalDate endDateExclusive)

```

**参数:**

*   【 Start date included–Start date included and cannot be blank.
*   End date private-end date private and cannot be empty.

**返回值:**period 的 between()函数返回给定开始日期和结束日期之间的时间段。

下面是上面功能的实现:

```
// Java code to show the period
// between given start and end date
import java.time.LocalDate;
import java.time.Period;

public class PeriodClass {

    // Function to calculate period between
    // start and end date
    static void calculatePeriod(LocalDate startDate,
                                LocalDate endDate)
    {
        Period period = Period.between(startDate, endDate);
        System.out.println("Period between start and end "
                           + "date is : " + period);
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Start date
        LocalDate startDate = LocalDate.parse("2017-02-13");

        // End date
        LocalDate endDate = LocalDate.parse("2018-08-20");

        calculatePeriod(startDate, endDate);
    }
}
```

**输出:**

```
Period between start and end date is : P1Y6M7D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # between-Java . time . local date-Java . time . local date-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#between-java.time.LocalDate-java.time.LocalDate-)
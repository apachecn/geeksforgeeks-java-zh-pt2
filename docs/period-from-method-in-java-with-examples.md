# Java 中从()方法开始的时间段，示例

> 原文:[https://www . geesforgeks . org/period-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-from-method-in-java-with-examples/)

Java 中 Period 类的 from()方法用于从给定的时间量中获取 Period 的实例。

此函数根据参数中给出的数量获得一个周期。时间计数表示时间量，可以是基于日期的，也可以是基于时间的。

**语法:**

```
public static Period from(TemporalAmount amount)
```

**参数:**此方法接受单个参数*量*。这个金额是我们需要转换成期间的金额。

**返回值:**该函数返回与给定金额相等的期间。

**异常:**

*   **Date-time exception** –If it cannot be converted into a period, a date-time exception will be thrown.
*   **Arithmetic exception** –If the number of years, months or days exceeds an integer, it will throw an arithmetic exception.

下面程序举例说明上面的方法:

```
// Java code to show the function from()
// which represents the period of given amount
import java.time.Period;

public class PeriodClassGfG {

    // Function to convert given amount to period
    static void convertToPeriod(int year, int months, int days)
    {
        Period period = Period.from(Period.of(year, months, days));

        System.out.println(period);
    }

    // Driver code
    public static void main(String[] args)
    {

        int year = 20, months = 13, days = 17;
        Period period = Period.from(Period.of(year, months, days));

        convertToPeriod(year, months, days);
    }
}
```

**输出:**

```
P20Y13M17D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # from-Java . time . temporal mount-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#from-java.time.temporal.TemporalAmount-)
# 年月直到()Java 中的方法示例

> 原文:[https://www . geesforgeks . org/year-month-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-until-method-in-java-with-examples/)

**直到()**方法的**年月**类用来计算两个年月对象之间的时间量使用时间间隔。起点和终点是这个，指定的年月作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，代表两个年月之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 为结束日期，不含，转换为年月，单位为计量金额的单位。

**返回值:**此方法返回今年月到年末月之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果金额无法计算，或者结束时间无法转换为年月。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```
// Java program to demonstrate
// YearMonth.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth objects
        YearMonth y1 = YearMonth.of(2018, 12);
        YearMonth y2 = YearMonth.of(2015, 10);

        // apply until the method of YearMonth class
        long result
            = y2.until(y1,
                       ChronoUnit.YEARS);

        // print results
        System.out.println("Result in YEARS: "
                           + result);
    }
}
```

**Output:**

```
Result in YEARS: 3

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth objects
        YearMonth y1 = YearMonth.of(2018, 12);
        YearMonth y2 = YearMonth.of(2015, 10);

        // apply until the method of YearMonth class
        long result
            = y1.until(y2,
                       ChronoUnit.MONTHS);

        // print results
        System.out.println("Result in MONTHS: "
                           + result);
    }
}
```

**Output:**

```
Result in MONTHS: -38

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html #直到(java.time.temporal.Temporal，Java . time . temporal alunit)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))
# Java 中的 ZonedDateTime plus()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plus-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有两种类型的 plus()方法。

### 加(long amountToAdd，temporalunit unit)

**plus()** 一个 **ZonedDateTime** 类的方法，用于返回添加了指定数量单位的该日期时间的副本。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。

**语法:**

```
public ZonedDateTime plus(long amountToAdd,
                          TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToAdd:** 是要添加到结果中的单位数量，可能为负数
*   **单位:**是要添加的量的单位。

**返回值:**此方法基于此日期时间返回**区域日期时间**，并添加指定的金额。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法添加。
*   **unsupportedtemporaltypexception**:如果不支持该单元。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了 plus()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.plus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // add 30 Months to ZonedDateTime
        ZonedDateTime value
            = zonedlt.plus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("ZonedDateTime after"
                           + " adding Months: \n"
                           + value);
    }
}
```

**Output:**

```
ZonedDateTime after adding Months: 
2021-06-06T19:21:12.123+05:30[Asia/Calcutta]

```

### amounttoadd 临时挂载)

**plus()** 一个 **ZonedDateTime** 类的方法，用于返回该日期时间的副本，并将指定的数量添加到日期时间中。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public ZonedDateTime plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**此方法基于此日期时间返回**区域日期时间**，并进行加法运算。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法添加。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了 plus()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.plus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // add 100 Days to ZonedDateTime
        ZonedDateTime value
            = zonedlt.plus(Period.ofDays(100));

        // print result
        System.out.println("ZonedDateTime after"
                           + " adding Days: \n"
                           + value);
    }
}
```

**Output:**

```
ZonedDateTime after adding Days: 
2019-03-16T19:21:12.123+05:30[Asia/Calcutta]

```

**参考:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plus(Java . time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#plus(java.time.temporal.TemporalAmount))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plus(long，Java . time . temporal unit)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#plus(long, java.time.temporal.TemporalUnit))
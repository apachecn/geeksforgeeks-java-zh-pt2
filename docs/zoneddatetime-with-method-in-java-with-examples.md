# Java 中带()方法的 ZonedDateTime 示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-with-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用 **ZonedDateTime** 类的**方法来调整这个日期时间，调整后返回调整后的日期时间的副本。使用指定的调整器策略对象进行调整。ZonedDateTime 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public ZonedDateTime with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法根据所做的调整返回一个 ZonedDateTime。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " adjustment: "
                           + zoneddatetime);

        // apply with method of ZonedDateTime class
        ZonedDateTime zt
            = zoneddatetime
                  .with(Month.SEPTEMBER)
                  .with(TemporalAdjusters.firstDayOfMonth());

        // print instance
        System.out.println("ZonedDateTime after"
                           + " adjustment: "
                           + zt);
    }
}
```

**Output:**

```
ZonedDateTime before adjustment: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime after adjustment: 2018-09-01T19:21:12.123+05:30[Asia/Calcutta]

```

### 带(临时字段，长新值)

**使用 **ZonedDateTime** 类的(临时字段，长新值)**方法将指定字段设置为新值，并返回新日期时间的副本。此方法可用于更改任何受支持的字段，如年、月或月中的某一天。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。
在某些情况下，更改指定的字段会导致结果日期时间无效，例如将月份从 1 月 31 日更改为 2 月会使当月的某一天无效。在这种情况下，字段负责解析日期。通常，它会选择以前的有效日期，在本例中是二月的最后一个有效日期。ZonedDateTime 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public ZonedDateTime with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法返回一个基于此的带指定字段集的 ZonedDateTime。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " applying method: "
                           + zoneddatetime);

        // apply with method of ZonedDateTime class
        ZonedDateTime zt
            = zoneddatetime.with(
                ChronoField.HOUR_OF_DAY, 13);

        // print instance
        System.out.println("ZonedDateTime after"
                           + " applying method: "
                           + zt);
    }
}
```

**Output:**

```
ZonedDateTime before applying method: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime after applying method: 2018-12-06T13:21:12.123+05:30[Asia/Calcutta]

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#with(java.time.temporal.TemporalField, long))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#with(java.time.temporal.TemporalAdjuster))
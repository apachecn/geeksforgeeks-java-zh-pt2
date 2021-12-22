# Java 中带()方法的 OffsetDateTime 示例

> 原文:[https://www . geeksforgeeks . org/offset datetime-with-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-with-method-in-java-with-examples/)

在 OffsetDateTime 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用 **OffsetDateTime** 类的(临时调整调节器)**方法，使用临时调整器调整该 OffsetDateTime，调整后返回调整后的 OffsetDateTime 的副本。使用指定的调整器策略对象进行调整。OffsetDateTime 的这个实例是不可变的，不受此方法调用的影响。

**语法:**

```
public OffsetDateTime with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法基于此返回一个带调整的 OffsetDateTime。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// OffsetDateTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetDateTime object
        OffsetDateTime off
            = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // print instance
        System.out.println("OffsetDateTime before"
                           + " adjustment: "
                           + off);

        // apply with method of OffsetDateTime class
        OffsetDateTime updatedlocal
            = off.with(Month.JUNE)
                  .with(TemporalAdjusters
                            .firstDayOfMonth());

        // print instance
        System.out.println("OffsetDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```
OffsetDateTime before adjustment: 2018-12-12T13:30:30+05:00
OffsetDateTime after adjustment: 2018-06-01T13:30:30+05:00

```

### 带(临时字段，长新值)

**使用 **OffsetDateTime** 类的(TemporalField，long newValue)** 方法，用于将 OffsetDateTime 的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何受支持的字段，例如年、月或月中的某一天。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。OffsetDateTime 的这个实例是不可变的，不受此方法调用的影响。

**语法:**

```
public OffsetDateTime with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法基于此返回一个带指定字段集的 OffsetDateTime。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// OffsetDateTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetDateTime object
        OffsetDateTime off
            = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // print instance
        System.out.println("OffsetDateTime before"
                           + " adjustment: "
                           + off);

        // apply with method of OffsetDateTime class
        OffsetDateTime updatedlocal
            = off.with(ChronoField.DAY_OF_MONTH, 31);

        // print instance
        System.out.println("OffsetDateTime after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
OffsetDateTime before adjustment: 2018-12-12T13:30:30+05:00
OffsetDateTime after applying method: 2018-12-31T13:30:30+05:00

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#with(java.time.temporal.TemporalAdjuster))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#with(java.time.temporal.TemporalField, long))
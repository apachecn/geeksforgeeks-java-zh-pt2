# 年用()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/year-with-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-with-method-in-java-with-examples/)

在 Year 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用**年**类的(临时调整者)**方法使用临时调整者来调整本年度，调整后返回调整年度的副本。使用指定的调整器策略对象进行调整。Year 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public Year with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法基于此返回一年，并进行调整。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// Year.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Year object
        Year yr
            = Year.of(2019);

        // print instance
        System.out.println("Year before"
                           + " adjustment: "
                           + yr);

        // apply with method of Year class
        Year updatedlocal = yr.with(Year.of(2012));

        // print instance
        System.out.println("Year after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```
Year before adjustment: 2019
Year after adjustment: 2012

```

### 带(临时字段，长新值)

**用 **Year** 类的(TemporalField field，long newValue)** 方法将指定的 Year 字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年份。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。Year 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public Year with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法以此为基础返回一年，并设置指定的字段。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// Year.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Year object
        Year yr
            = Year.of(2019);

        // print instance
        System.out.println("Year before"
                           + " applying method: "
                           + yr);

        // apply with method of Year class
        Year updatedlocal
            = yr.with(ChronoField.YEAR, 2100);

        // print instance
        System.out.println("Year after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
Year before applying method: 2019
Year after applying method: 2100

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#with(java.time.temporal.TemporalAdjuster))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#with(java.time.temporal.TemporalField, long))
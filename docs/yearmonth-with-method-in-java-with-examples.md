# 年月用()方法用 Java 举例

> 原文:[https://www . geesforgeks . org/year-month-with-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-with-method-in-java-with-examples/)

在 YearMonth 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用**年月**类的(临时调整者)**方法使用临时调整者调整本年度月，调整后返回调整年度月的副本。使用指定的调整器策略对象进行调整。YearMonth 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public YearMonth with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法根据调整后的值返回一个年月。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```java
// Java program to demonstrate
// YearMonth.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a YearMonth object
        YearMonth yr
            = YearMonth.of(2019, 12);

        // print instance
        System.out.println("YearMonth before"
                           + " adjustment: "
                           + yr);

        // apply with method of YearMonth class
        YearMonth updatedlocal
            = yr.with(YearMonth.of(2012, 12));

        // print instance
        System.out.println("YearMonth after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
YearMonth before adjustment: 2019-12
YearMonth after adjustment: 2012-12

```

### 带(临时字段，长新值)

**使用 **YearMonth** 类的(TemporalField field，long newValue)** 方法，用于将 YearMonth 的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年或月。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。YearMonth 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public YearMonth with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法根据指定的字段集返回一个年月。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```java
// Java program to demonstrate
// YearMonth.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a YearMonth object
        YearMonth yr
            = YearMonth.of(2019, 12);

        // print instance
        System.out.println("YearMonth before"
                           + " applying method: "
                           + yr);

        // apply with method of YearMonth class
        YearMonth updatedlocal
            = yr.with(ChronoField.YEAR, 2100);

        // print instance
        System.out.println("YearMonth after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
YearMonth before applying method: 2019-12
YearMonth after applying method: 2100-12

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#with(java.time.temporal.TemporalAdjuster))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#with(java.time.temporal.TemporalField, long))
# Java 中带()方法的 OffsetTime，示例

> 原文:[https://www . geesforgeks . org/offsettime-with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-with-method-in-java-with-examples/)

在 OffsetTime 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用**偏置时间**类的**方法用临时调整器调整了这个偏置时间，调整后返回调整后的偏置时间的副本。使用指定的调整器策略对象进行调整。OffsetTime 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public OffsetTime with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法在进行调整的基础上返回一个偏移量。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime off
            = OffsetTime.parse("19:19:50+06:00");

        // print instance
        System.out.println("OffsetTime before"
                           + " adjustment: "
                           + off);

        // apply with method of OffsetTime class
        OffsetTime updatedlocal = off.with(LocalTime.NOON);

        // print instance
        System.out.println("OffsetTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
OffsetTime before adjustment: 19:19:50+06:00
OffsetTime after adjustment: 12:00+06:00

```

### 带(临时字段，长新值)

**用 **OffsetTime** 类的(TemporalField，long newValue)** 方法将 OffsetTime 的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。OffsetTime 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public OffsetTime with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法基于此返回一个带指定字段集的 OffsetTime。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime off
            = OffsetTime.parse("19:19:50+06:00");

        // print instance
        System.out.println("OffsetTime before"
                           + " applying method: "
                           + off);

        // apply with method of OffsetTime class
        OffsetTime updatedlocal
            = off.with(
                ChronoField.HOUR_OF_DAY, 23);

        // print instance
        System.out.println("OffsetTime after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
OffsetTime before applying method: 19:19:50+06:00
OffsetTime after applying method: 23:19:50+06:00

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsettime . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetTime.html#with(java.time.temporal.TemporalAdjuster))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsettime . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetTime.html#with(java.time.temporal.TemporalField, long))
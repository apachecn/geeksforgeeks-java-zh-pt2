# Java 中的 OffsetTime 直到()方法，示例

> 原文:[https://www . geesforgeks . org/offsettime-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-until-method-in-java-with-examples/)

**直到()**方法的**偏置时间**类用于计算两个偏置时间对象之间的时间量使用时间间隔。起点和终点是这个，指定的偏移量作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，代表两个偏移量之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 为结束日期，Exclusive 转换为 OffsetTime，unit 为计量金额的单位。

**返回值:**此方法返回此偏移时间和结束偏移时间之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果无法计算金额，或者结束时间无法转换为偏移时间。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```
// Java program to demonstrate
// OffsetTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create OffsetTime objects
        OffsetTime o1 = OffsetTime.parse("03:30:30+05:00");
        OffsetTime o2 = OffsetTime.parse("23:30:30+05:00");

        // apply until method of OffsetTime class
        long result
            = o1.until(o2,
                       ChronoUnit.MINUTES);

        // print results
        System.out.println("Result in MINUTES: "
                           + result);
    }
}
```

**Output:**

```
Result in MINUTES: 1200

```

**程序 2:**

```
// Java program to demonstrate
// OffsetTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create OffsetTime objects
        OffsetTime o1 = OffsetTime.parse("03:30:30+05:00");
        OffsetTime o2 = OffsetTime.parse("19:30:30+05:00");

        // apply until method of OffsetTime class
        long result
            = o1.until(o2,
                       ChronoUnit.HOURS);

        // print results
        System.out.println("Result in HOURS: "
                           + result);
    }
}
```

**Output:**

```
Result in HOURS: 16

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsettime . html #直到(java.time.temporal.Temporal，Java . time . temporal unit)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))
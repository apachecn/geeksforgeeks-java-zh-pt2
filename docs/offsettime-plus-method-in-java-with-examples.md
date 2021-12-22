# Java 中的 OffsetTime plus()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-plus-method-in-java-with-examples/)

在 OffsetTime 类中，根据传递给它的参数，有两种类型的 plus()方法。

### 加(long amountToAdd，temporalunit unit)

**plus()** 一个 **OffsetTime** 类的方法，用于返回这个 OffsetTime 的副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。这个 OffsetTime 对象是不可变的，不受这个方法调用的影响。

**语法:**

```
public OffsetTime plus(long amountToAdd,
                      TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToAdd** 可以为负数，也可以接受 **unit** 为要相加的金额单位，不为空。

**返回值:**该方法基于该偏移量返回**偏移量**，并添加指定的金额。

下面的程序说明了加号()方法:
**程序 1:**

```
// Java program to demonstrate
// OffsetTime.plus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create an OffsetTime object
        OffsetTime lt
            = OffsetTime.parse("12:14:10+13:00");

        // add 2 Hours to OffsetTime
        OffsetTime value
            = lt.plus(2, ChronoUnit.HOURS);

        // print result
        System.out.println("OffsetTime after adding 2 Hours: "
                           + value);
    }
}
```

**Output:**

```
OffsetTime after adding 2 Hours: 14:14:10+13:00

```

### amounttoadd 临时挂载)

**plus()** 一个 **OffsetTime** 类的方法，用于返回该 OffsetTime 的一个副本，其中指定的数量被添加到日期时间中。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public OffsetTime plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**该方法基于该偏移量返回**偏移量**，并进行加法运算，不为空

下面的程序说明了加号()方法:
**程序 1:**

```
// Java program to demonstrate
// OffsetTime.plus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime lt
            = OffsetTime.parse("12:14:10+13:00");

        // add 55 Minutes to OffsetTime
        OffsetTime value
            = lt.plus(Duration.ofMinutes(55));

        // print result
        System.out.println("OffsetTime after adding 55 Minutes: "
                           + value);
    }
}
```

**Output:**

```
OffsetTime after adding 55 Minutes: 13:09:10+13:00

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettimee . html # plus-Java . time .时态. tempalamount-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#plus-java.time.temporal.TemporalAmount-)
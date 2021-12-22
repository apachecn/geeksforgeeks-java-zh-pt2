# Java 中的年到()方法，示例

> 原文:[https://www . geesforgeks . org/year-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-until-method-in-java-with-examples/)

**直到()**年**类的**方法，用于使用时间单位计算两个年份对象之间的时间量。起点和终点是这个，指定的年份作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，表示两年之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 为结束日期，不含，转换为年份，单位为计量金额的单位。

**返回值:**此方法返回今年到年末的时间量。

**异常:**该方法抛出以下异常:

*   日期时间例外–如果无法计算金额，或者结束时间无法转换为年份。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```java
// Java program to demonstrate
// Year.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create Year objects
        Year y1 = Year.of(2018);
        Year y2 = Year.of(2015);

        // apply until the method of Year class
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

```java
Result in YEARS: 3

```

**程序 2:**

```java
// Java program to demonstrate
// Year.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create Year objects
        Year y1 = Year.of(2018);
        Year y2 = Year.of(2200);

        // apply until the method of Year class
        long result
            = y1.until(y2,
                       ChronoUnit.DECADES);

        // print results
        System.out.println("Result in DECADES: "
                           + result);
    }
}
```

**Output:**

```java
Result in DECADES: 18

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html #直到(java.time.temporal.Temporal，Java . time . temporal alunit)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))
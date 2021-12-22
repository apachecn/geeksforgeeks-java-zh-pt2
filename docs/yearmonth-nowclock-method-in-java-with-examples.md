# Java 中的年月现(时钟)方法，示例

> 原文:[https://www . geesforgeks . org/year month-now clock-in-Java-method-with-examples/](https://www.geeksforgeeks.org/yearmonth-nowclock-method-in-java-with-examples/)

**Java 中 **YearMonth** 类的 now(Clock clock)** 方法用于从指定的时钟获取当前的年-月。
**语法:**

```java
public static YearMonth
         now(Clock clock)
```

**参数:**此方法接受**时钟**作为代表要使用的时钟的参数。

**返回值:**此方法返回当前**年-月**。

下面的程序说明了 Java 中现在(时钟)的年月方法:

**程序 1:**

```java
// Java program to demonstrate
// YearMonth.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of YearMonth class
        YearMonth result
            = YearMonth.now(
                Clock.systemUTC());

        // print year and month both
        System.out.println(
            "YearMonth: "
            + result);
    }
}
```

**Output:**

```java
YearMonth: 2020-05

```

**程序 2:**

```java
// Java program to demonstrate
// YearMonth.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of YearMonth class
        YearMonth result
            = YearMonth.now(
                Clock.systemUTC());

        // print only year
        System.out.println("Year: "
                           + result.get(
                                 ChronoField.YEAR));
    }
}
```

**Output:**

```java
Year: 2020

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#now(java.time.Clock))
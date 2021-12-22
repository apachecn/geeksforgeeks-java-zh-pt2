# Java 中的 ZonedDateTime plusDays()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plus days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusdays-method-in-java-with-examples/)

Java 中 **ZonedDateTime** 类的 **plusDays()** 方法用于在这个 ZonedDateTime 实例中添加指定的天数，并返回一个 ZonedDateTime 的副本。此方法将作为参数传递的天数添加到本地日期时间，然后将其转换回区域数据时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime plusDays(long days)

```

**参数:**此方法接受单个参数*天数*，代表要添加的天数，可以是负数。

**返回值:**该方法返回一个基于该日期时间加上天数的**区域时间**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusDays()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.plusDays() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " adding days: " + zoneddatetime);

        // add 3 days
        ZonedDateTime returnvalue
            = zoneddatetime.plusDays(3);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding days: " + returnvalue);
    }
}
```

**Output:**

```java
ZonedDateTime before adding days: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime after  adding days: 2018-12-09T19:21:12.123+05:30[Asia/Calcutta]

```

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.plusDays() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse("2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " adding days: " + zoneddatetime);

        // add 20 days
        ZonedDateTime returnvalue
            = zoneddatetime.plusDays(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding days: " + returnvalue);
    }
}
```

**Output:**

```java
ZonedDateTime before adding days: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ZonedDateTime after  adding days: 2018-11-14T23:12:31.123+01:00[Europe/Paris]

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusDays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#plusDays(long))
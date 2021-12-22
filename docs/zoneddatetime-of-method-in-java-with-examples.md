# Java 中()方法的 ZonedDateTime 示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-in-Java-method-in-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有三种类型的()方法。

### of(整年、整月、整日、整小时、整分钟、整秒、整纳秒、区域 Id 区域)

类的方法，用于从年、月、日、小时、分钟、秒、纳秒和时区中获取 ZonedDateTime 的实例。

**语法:**

```java
public static ZonedDateTime of(int year, int month, 
                               int dayOfMonth,
                               int hour, int minute,
                               int second, int nanoOfSecond,
                               ZoneId zone)

```

**参数:**该方法接受八个不同的参数:

*   年份–要代表的年份，从最小年到最大年。
*   月份–一年中的月份，从 1 月 1 日到 12 月 12 日。
*   从 1 到 31 的一个月中的某一天。
*   小时–要表示的一天中的小时，从 0 到 23。
*   分钟–要表示的分钟，从 0 到 59。
*   秒–要表示的分钟秒数，从 0 到 59。
*   纳米秒–表示从 0 到 999，999，999 的纳米秒。
*   区域–时区，不为空。

**返回值:**此方法返回偏移日期时间。

**异常:**如果任何字段的值超出范围，或者月中的某一天对于月-年无效，该方法将抛出**日期时间异常**。

以下程序说明()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.of() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ZonedDateTime object
        // using of method
        ZonedDateTime lt
            = ZonedDateTime.of(
                2020, 12, 3, 12, 20, 59,
                90000, ZoneId.systemDefault());

        // print result
        System.out.println("ZonedDateTime : "
                           + lt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2020-12-03T12:20:59.000090Z[Etc/UTC]

```

### 任务(LocalDate、LocalTime、ZoneId zone)

用于从本地日期、时间和区域返回区域时间实例的**区域时间类的**方法。****

**语法:**

```java
public static ZonedDateTime of(LocalDate date,
                               LocalTime time,
                               ZoneId zone)

```

**参数:**该方法接受三个不同的参数:

*   日期–当地日期
*   时间–当地时间
*   区域–时区

**返回值:**此方法返回偏移日期时间。

以下程序说明()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.of() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime
        LocalDate localdate
            = LocalDate.parse("2020-12-30");

        // create a LocalTime
        LocalTime localtime
            = LocalTime.parse("17:52:49");

        // create a zoneid
        ZoneId zid
            = ZoneId.of("Europe/Paris");

        // create an ZonedDateTime object
        // using of() method
        ZonedDateTime zt
            = ZonedDateTime.of(localdate,
                               localtime, zid);

        // print result
        System.out.println("ZonedDateTime : "
                           + zt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2020-12-30T17:52:49+01:00[Europe/Paris]

```

### of(LocalDateTime localDateTime，ZoneId zone)

类的方法，用于从 localdatetime 和 zone 返回 ZonedDateTime 的实例。所有这些 localdatetime 和 zone 都作为参数传递。

**语法:**

```java
public static ZonedDateTime of(LocalDateTime localDateTime,
                               ZoneId zone)

```

**参数:**该方法接受两个不同的参数:

*   本地日期时间–本地日期时间
*   时间–当地时间

**返回值:**此方法返回偏移日期时间。

以下程序说明()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.of() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime
        LocalDateTime local
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // create a zoneid
        ZoneId zid = ZoneId.of("Europe/Paris");

        // create an ZonedDateTime object
        // using of()
        ZonedDateTime zt
            = ZonedDateTime.of(
                local, zid);

        // print result
        System.out.println("ZonedDateTime : "
                           + zt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2018-11-03T12:45:30+01:00[Europe/Paris]

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # of(int，int，int，int，int，int，java.time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#of(int, int, int, int, int, int, int, java.time.ZoneId))
T6】https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # of(Java . time . local date，java.time.LocalTime，Java . time。
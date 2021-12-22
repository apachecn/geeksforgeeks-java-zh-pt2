# Java 中的 ZonedDateTime isSupported()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-issupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-issupported-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有两种类型的 isSupported()方法。

### 问题支持(临时字段)

**isSupported()** 一个 **ZonedDateTime** 类的方法，用来检查指定的字段是否被 ZonedDateTime 类支持，也就是说使用这个方法我们可以检查这个 ZonedDateTime 是否可以查询到指定的字段。

计时场支持的字段有:

*   第二纳米
*   微秒
*   毫欧秒
*   即时 _ 秒
*   第二分钟
*   纳米日
*   微观 _OF_DAY
*   百万分之日
*   第二天
*   分钟/小时
*   每天分钟
*   AMPM 时间
*   AMPM 时间
*   一天中的小时
*   一天中的钟点
*   当日 AMPM
*   星期几
*   对齐 _ 周 _ 月 _ 日
*   年 _ 月 _ 日 _ 周 _ 对齐
*   月日
*   一年中的第 _ 天
*   纪元日
*   每月的第 _ 周
*   对齐 _ 周 _ 年
*   年月日
*   prolective _ MONTH
*   纪元年
*   年
*   时代
*   即时 _ 秒
*   偏移量 _ 秒

所有其他时间域实例都将返回 false。

**语法:**

```
public boolean isSupported(TemporalField field)

```

**参数:**此方法接受一个单参数**字段**，即要检查的字段。

**返回值:**如果该日期时间支持该字段，则该方法返回**布尔值【true，否则返回 false。**

下面的程序说明了 isSupported()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zdt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // check ALIGNED_WEEK_OF_YEAR
        // is supported in ZonedDateTime
        boolean value
            = zdt.isSupported(
                ChronoField.ALIGNED_WEEK_OF_YEAR);

        // print result
        System.out.println("ALIGNED_WEEK_OF_YEAR "
                           + "Field is supported: "
                           + value);
    }
}
```

**Output:**

```
ALIGNED_WEEK_OF_YEAR Field is supported: true

```

### 发行支持(临时单位)

**isSupported()** 一个 **ZonedDateTime** 类的方法用来检查指定的单位是否被 ZonedDateTime 类支持意味着使用这个方法我们可以检查这个 ZonedDateTime 是否可以查询到指定的单位。

计时单位支持的字段有:

*   纳诺斯
*   MICROS
*   莫利斯
*   秒
*   分钟
*   小时
*   半天
*   天
*   周；星期
*   月份
*   年
*   数十年
*   世纪
*   一千年
*   年代

所有其他计时单位实例将返回 false。

**语法:**

```
public boolean isSupported(TemporalUnit unit)

```

**参数:**该方法只接受一个参数**单位**，即要检查的单位。

**返回值:**如果该日期时间支持该字段，则该方法返回**布尔值【true，否则返回 false。**

下面的程序说明了 isSupported()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.isSupported() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime lt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // check MILLENNIA ChronoUnit supported
        // in ZonedDateTime
        boolean value
            = lt.isSupported(ChronoUnit.MILLENNIA);

        // print result
        System.out.println("ChronoUnit MILLENNIA "
                           + "is  supported: "
                           + value);
    }
}
```

**Output:**

```
ChronoUnit MILLENNIA is  supported: true

```

**参考:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#isSupported(java.time.temporal.TemporalField))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # isSupported(Java . time . temporal unit)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#isSupported(java.time.temporal.TemporalUnit))
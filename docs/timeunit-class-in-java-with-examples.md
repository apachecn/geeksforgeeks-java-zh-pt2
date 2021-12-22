# Java 中的时间单位类，示例

> 原文:[https://www . geesforgeks . org/time unit-in-Java-class-with-examples/](https://www.geeksforgeeks.org/timeunit-class-in-java-with-examples/)

**时间单位**是[*****Java . util . concurrent*****包****](https://www.geeksforgeeks.org/java-util-concurrent-package/) **中可用的枚举。时间单位顾名思义处理时间单位。时间单位以给定的粒度单位提供时间表示。它提供了跨时间单位转换时间的方法。时间单位有助于了解给定时间应该如何解释，即应该考虑哪个时间单位。持续时间之间的微小差异，如微秒和纳秒，可以使用时间单位计算出来。它用于执行定时和延迟操作。**

**它支持纳秒、微秒、毫秒、秒、分钟、小时和天单位。对于这些单位，TimeUnit 指定对应的枚举常数:**

***   Nanosecond: one thousandth of a microsecond*   Microsecond: one thousandth of a millisecond*   Millisecond: thousandth of a second*   Seconds: one second*   Minutes: 60 seconds*   Hour: 60 minutes*   Day: 24 hours.**

****例 1:****

 **## 爪哇

```java
// Java program to demonstrate TimeUnit Class

import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        long hours = 96;

        // Convert given time (hours)in days
        long days = TimeUnit.DAYS.convert(hours, TimeUnit.HOURS);

        // Convert days in minutes
        long minutes = TimeUnit.MINUTES.convert(days, TimeUnit.DAYS);

        System.out.println(hours + " Hours = " + days
                           + " Days = " + +minutes
                           + " Minutes");

        // Convert given time (minutes) to microseconds
        long micros = TimeUnit.MINUTES.toMicros(minutes);
        System.out.println(minutes + " Minutes = " + micros
                           + " Microseconds");

        // Convert given time (microseconds) to seconds
        long seconds = TimeUnit.MICROSECONDS.toSeconds(micros);
        System.out.println(micros + " Microseconds = "
                           + seconds + " Seconds");

        // Create TimeUnit object of type Minutes
        TimeUnit time = TimeUnit.valueOf("MINUTES");
        System.out.println("TimeUnit object type: " + time);
    }
}
```** ****输出**

```java
96 Hours = 4 Days = 5760 Minutes
5760 Minutes = 345600000000 Microseconds
345600000000 Microseconds = 345600 Seconds
TimeUnit object type: MINUTES
```**
# Java 中()方法的 OffsetDateTime，示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-of-in-Java-of-method-in-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-of-method-in-java-with-examples/)

Java 中 **OffsetDateTime** 类的**(int year，int month，int day，int hour，int minute，int second，int 纳秒，ZoneOffset offset)** 方法用于根据传递的年、月、日、小时、分钟、秒、纳秒和偏移量的值创建 **OffsetDateTime** 的实例。在该方法中，年、月、日、小时、分钟、秒和纳秒的值以整数格式传递，并且该方法基于这些值返回日期-时间。

**语法:**

```java
public static OffsetDateTime of(int year,
                                int month,
                                int day,
                                int hour,
                                int minute,
                                int second,
                                int nanosecond,
                                ZoneOffset offset)

```

**参数:**该方法接受 8 个参数。

*   **年**–整数型，代表年份。它从最小年到最大年不等。
*   **月**–整数型，代表一年中的月份。从 1 月 1 日到 12 月 12 日不等。
*   **日**–整数类型，代表一个月中的某一天。从 1 到 31 不等。
*   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
*   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。
*   **秒**–整数类型，表示分钟的秒。从 0 到 59 不等。
*   **纳秒**–整数型，代表纳秒。它从 0 到 999999999 不等。
*   **偏移**–属于区域偏移类型，代表区域偏移。它不应为空。

**返回值:**该方法返回**偏移日期时间**。

**异常:**如果任何字段值超出范围或月中的某一天对于月-年无效，此方法将抛出**日期时间异常**。

下面的程序说明了 Java 中 OffsetDateTime 类的()方法:

**程序 1:**

```java
// Java program to demonstrate
// OffsetDateTime of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(
        String[] args)
    {
        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.of(
                2020, 5, 20, 9, 10, 40,
                50000, ZoneOffset.UTC);

        // Print date-time
        System.out.println(
            "DATE-TIME: "
            + offsetdatetime);
    }
}
```

**Output:**

```java
DATE-TIME: 2020-05-20T09:10:40.000050Z

```

**程序 2:**

```java
// Java program to demonstrate
// OffsetDateTime of() method
import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.of(
                2020, 5, 20, 9, 10, 40,
                20000, ZoneOffset.ofHoursMinutes(
                           5, 30));

        // Print date-time
        System.out.println(
            "DATE-TIME: "
            + offsetdatetime);
    }
}
```

**Output:**

```java
DATE-TIME: 2020-05-20T09:10:40.000020+05:30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # of(int，int，int，int，int，int，int，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#of(int, int, int, int, int, int, int, java.time.ZoneOffset))
# Java 中(LocalDateTime)方法的 OffsetDateTime，示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-of localdatetime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-oflocaldatetime-method-in-java-with-examples/)

Java 中 **OffsetDateTime** 类的(LocalDateTime，ZoneOffset offset) 方法的**用于根据给定的日期-时间和偏移量实例创建 **OffsetDateTime** 的实例。此方法使用指定的本地日期时间和偏移量创建一个 OffsetDateTime。**

**语法:**

```java
public static OffsetDateTime
       of(LocalDateTime dateTime,
          ZoneOffset offset)

```

**参数:**该方法接受两个参数:

*   **日期时间**–表示本地日期时间。
*   **偏移**–表示区域偏移。

**返回值:**该方法返回**偏移日期时间**。

**异常:**此方法不抛出任何异常。

下面的程序说明了 Java 中 OffsetDateTime 类的(LocalDateTime，ZoneOffset)方法:

**程序 1:**

```java
// Java program to demonstrate
// OffsetDateTime of(LocalDateTime,
// ZoneOffset) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create LocalDateTime object
        LocalDateTime dateTime
            = LocalDateTime.parse(
                "2020-05-28T04:12:50");

        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.of(
                dateTime, ZoneOffset.UTC);

        // Print date-time
        System.out.println("DATE-TIME: "
                           + offsetdatetime);
    }
}
```

**Output:**

```java
DATE-TIME: 2020-05-28T04:12:50Z

```

**程序 2:**

```java
// Java program to demonstrate
// OffsetDateTime of(LocalDateTime,
// ZoneOffset) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create LocalDateTime object
        LocalDateTime dateTime
            = LocalDateTime.of(
                2020, 5, 28, 4, 12, 50);

        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.of(
                dateTime, ZoneOffset.UTC);

        // Print date-time
        System.out.println("DATE-TIME: "
                           + offsetdatetime);
    }
}
```

**Output:**

```java
DATE-TIME: 2020-05-28T04:12:50Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # of(Java . time . local datetime，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#of(java.time.LocalDateTime, java.time.ZoneOffset))
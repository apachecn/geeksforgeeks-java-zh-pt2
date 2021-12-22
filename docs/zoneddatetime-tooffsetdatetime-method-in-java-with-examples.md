# Java 中的 ZonedDateTime toOffsetDateTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-tooffsetdatetime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-tooffsetdatetime-method-in-java-with-examples/)

**区域日期时间**类的 **toOffsetDateTime()** 方法用于将该日期时间转换为偏移日期时间，区域标识被忽略。

**语法:**

```java
public OffsetDateTime toOffsetDateTime()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**偏移日期时间**，表示相同的本地日期时间和偏移。

下面的程序说明了 toOffsetDateTime()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.toOffsetDateTime() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print result
        System.out.println("ZonedDateTime: " + zoneddatetime);

        // get OffsetDateTime
        OffsetDateTime value = zoneddatetime.toOffsetDateTime();

        // print result
        System.out.println("OffsetDateTime: " + value);
    }
}
```

**输出:**

```java
ZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
OffsetDateTime: 2018-12-06T19:21:12.123+05:30

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.toOffsetDateTime() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print result
        System.out.println("ZonedDateTime: " + zoneddatetime);

        // get OffsetDateTime
        OffsetDateTime value = zoneddatetime.toOffsetDateTime();

        // print result
        System.out.println("OffsetDateTime: " + value);
    }
}
```

**输出:**

```java
ZonedDateTime: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
OffsetDateTime: 2018-10-25T23:12:31.123+02:00

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # toOffsetDateTime()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#toOffsetDateTime())
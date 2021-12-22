# Java 中的 ZonedDateTime with fixedoffsetzone()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with fixedoffsetzone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withfixedoffsetzone-method-in-java-with-examples/)

**ZonedDateTime** 类的 **withFixedOffsetZone()** 方法用于返回该 ZonedDateTime 对象的副本，其中区域标识设置为偏移量。此方法返回一个区域数据时间，其中区域标识与 getOffset()相同。返回的 ZonedDateTime 的本地日期时间、偏移量和即时时间将与此日期时间相同。

**语法:**

```java
public ZonedDateTime withFixedOffsetZone()

```

**参数:**该方法不接受参数。

**返回值:**该方法返回一个**区域数据时间**，区域标识设置为偏移量。

下面的程序说明了 withFixedOffsetZone()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.withFixedOffsetZone() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime
                  .ofLocal(
                      LocalDateTime.of(2018, 11, 4, 1, 25, 43),
                      ZoneId.of("US/Central"),
                      ZoneOffset.ofHours(-6));

        // print ZonedDateTime
        System.out.println("Before withFixedOffsetZone(): "
                           + zonedDT);

        // apply withFixedOffsetZone()
        ZonedDateTime zonedDT2
            = zonedDT.withFixedOffsetZone();

        // print ZonedDateTime after withFixedOffsetZone()
        System.out.println("After withFixedOffsetZone(): "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withFixedOffsetZone(): 2018-11-04T01:25:43-06:00[US/Central]
After withFixedOffsetZone(): 2018-11-04T01:25:43-06:00

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.withFixedOffsetZone() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime.now();

        // print ZonedDateTime
        System.out.println("Before withFixedOffsetZone(): "
                           + zonedDT);

        // apply withFixedOffsetZone()
        ZonedDateTime zonedDT2
            = zonedDT.withFixedOffsetZone();

        // print ZonedDateTime after withFixedOffsetZone()
        System.out.println("After withFixedOffsetZone(): "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withFixedOffsetZone(): 2018-12-17T05:16:41.417Z[Etc/UTC]
After withFixedOffsetZone(): 2018-12-17T05:16:41.417Z

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with fixedoffsetzone()
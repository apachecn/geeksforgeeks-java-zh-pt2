# Java 中的 ZonedDateTime with arlierfoffsettoverlap()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-witharrieoffsetatoverlap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withearlieroffsetatoverlap-method-in-java-with-examples/)

在本地时间线重叠处将区域偏移更改为两个有效偏移中较早的一个后，使用**区域数据时间**类的**witharlieroffsettoverlap()**方法返回该区域数据时间对象的副本。当夏令时结束，一小时回到时间线时，就会发生重叠。因此，本地日期时间有两个有效的偏移量，用 withEarlierOffsetAtOverlap 方法调用将返回一个带有两个区域中较早者的区域数据时间。如果此方法不是重叠时调用，则返回。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime withEarlierOffsetAtOverlap()

```

**参数:**该方法不接受参数。

**返回值:**该方法根据该日期时间返回一个**区域日期时间**，偏移量较早。

下面的程序说明了 withEarlierOffsetAtOverlap()方法:

**程序 1:**

```java
// Java program to demonstrate
// withEarlierOffsetAtOverlap() method

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
        System.out.println("Before"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT);

        // apply withEarlierOffsetAtOverlap()
        ZonedDateTime zonedDT2
            = zonedDT.withEarlierOffsetAtOverlap();

        // print ZonedDateTime after
        // withEarlierOffsetAtOverlap()
        System.out.println("\nAfter"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withEarlierOffsetAtOverlap():
 2018-11-04T01:25:43-06:00[US/Central]

After withEarlierOffsetAtOverlap():
 2018-11-04T01:25:43-05:00[US/Central]

```

**程序二:**

```java
// Java program to demonstrate
// withEarlierOffsetAtOverlap() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime
                  .ofLocal(
                      LocalDateTime.of(2021, 11, 07, 1, 05, 53),
                      ZoneId.of("US/Central"),
                      ZoneOffset.ofHours(-6));

        // print ZonedDateTime
        System.out.println("Before"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT);

        // apply withEarlierOffsetAtOverlap()
        ZonedDateTime zonedDT2
            = zonedDT.withEarlierOffsetAtOverlap();

        // print ZonedDateTime after
        // withEarlierOffsetAtOverlap()
        System.out.println("\nAfter"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withEarlierOffsetAtOverlap():
 2021-11-07T01:05:53-06:00[US/Central]

After withEarlierOffsetAtOverlap():
 2021-11-07T01:05:53-05:00[US/Central]

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # witharrieoffsetatoverlap()
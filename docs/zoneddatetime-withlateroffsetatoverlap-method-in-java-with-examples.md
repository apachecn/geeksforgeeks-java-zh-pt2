# Java 中的 ZonedDateTime with lateraoffsettoverlap()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with lateraoffsetatoverlap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withlateroffsetatoverlap-method-in-java-with-examples/)

**ZonedDateTime** 类的**with lateroffsettoverlap()**方法用于在本地时间线重叠处将区域偏移更改为两个有效偏移中的较晚者后，返回该 ZonedDateTime 对象的副本。当夏令时结束，一小时回到时间线时，就会发生重叠。为此，本地日期时间有两个有效的偏移量，调用 withLaterOffsetAtOverlap 方法将返回一个带有两个区域中较晚的一个的 ZonedDateTime。如果此方法不是重叠时调用，则返回。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime withLaterOffsetAtOverlap()

```

**参数:**该方法不接受参数。

**返回值:**该方法根据该日期时间返回一个**区域日期时间**,该日期时间有后一个偏移量。

下面的程序说明了 withLaterOffsetAtOverlap()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.withLaterOffsetAtOverlap() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime.of(
                LocalDateTime.of(2018, 11, 4, 1, 25, 43),
                ZoneId.of("US/Central"));

        // print ZonedDateTime
        System.out.println("Before withLaterOffsetAtOverlap(): "
                           + zonedDT);

        // apply withLaterOffsetAtOverlap()
        ZonedDateTime zonedDT2
            = zonedDT.withLaterOffsetAtOverlap();

        // print ZonedDateTime after withLaterOffsetAtOverlap()
        System.out.println("After withLaterOffsetAtOverlap(): "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withLaterOffsetAtOverlap(): 2018-11-04T01:25:43-05:00[US/Central]
After withLaterOffsetAtOverlap(): 2018-11-04T01:25:43-06:00[US/Central]

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.withLaterOffsetAtOverlap() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime.of(
                LocalDateTime.of(2021, 11, 07, 1, 05, 53),
                ZoneId.of("US/Central"));

        // print ZonedDateTime
        System.out.println("Before withLaterOffsetAtOverlap(): "
                           + zonedDT);

        // apply withLaterOffsetAtOverlap()
        ZonedDateTime zonedDT2
            = zonedDT.withLaterOffsetAtOverlap();

        // print ZonedDateTime after withLaterOffsetAtOverlap()
        System.out.println("After withLaterOffsetAtOverlap(): "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withLaterOffsetAtOverlap(): 2021-11-07T01:05:53-05:00[US/Central]
After withLaterOffsetAtOverlap(): 2021-11-07T01:05:53-06:00[US/Central]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with lateroffsetatoverlap()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#withLaterOffsetAtOverlap())
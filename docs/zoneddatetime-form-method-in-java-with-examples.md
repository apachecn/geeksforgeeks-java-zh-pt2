# Java 中的 ZonedDateTime form()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-form-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-form-method-in-java-with-examples/)

Java 中 **ZonedDateTime** 类的 **from()** 方法用于从作为参数传递的 TemporalAccessor 对象中获取 ZonedDateTime 的实例。临时进程代表一组任意的日期和时间信息，该方法有助于根据指定的临时进程对象获得一个即时的区域数据时间。

**语法:**

```java
public static ZonedDateTime 
                from(TemporalAccessor temporal)

```

**参数:**该方法接受单个参数**时态**，表示要转换的时态对象。这是一个强制参数，不应为空。

**返回值:**该方法返回一个**分区的日期时间**。

**异常:**如果无法转换为区域数据时间，该方法将抛出**日期时间异常**。

以下程序说明了 from()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime.now();

        // create a ZonedDateTime object using
        // from() method
        ZonedDateTime result = ZonedDateTime.from(zonedDT);

        // print result
        System.out.println("ZonedDateTime: "
                           + result);
    }
}
```

**Output:**

```java
ZonedDateTime: 2018-12-12T19:03:06.445Z[Etc/UTC]

```

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetDateTime object
        OffsetDateTime offset
            = OffsetDateTime.now();

        // create a ZonedDateTime object using
        // from() method
        ZonedDateTime result = ZonedDateTime.from(offset);

        // print result
        System.out.println("ZonedDateTime: "
                           + result);
    }
}
```

**Output:**

```java
ZonedDateTime: 2018-12-12T19:03:09.523Z

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # from(Java . time . temporalacessor)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#from(java.time.temporal.TemporalAccessor))
# Java 中的 ZonedDateTime ofInstant()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-of instant-class-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-ofinstant-class-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有两种类型的 ofInstant()方法。

### 办公室常量(Instant、ZoneId zone)

**ofInstant()** 一个 **ZonedDateTime** 类的方法，用于从一个作为参数传递给该方法的 Instant 和 zoneId 创建一个 ZonedDateTime 实例。当您有一个即时对象和一个区域标识，并且您想要创建一个同时包含这两个区域标识的时钟时，这是一个非常有用的方法。

**语法:**

```java
public static ZonedDateTime ofInstant(Instant instant,
                                      ZoneId zone)

```

**参数:**该方法接受两个参数**瞬间**即创建日期时间的瞬间，不能为空，
T5 区即时区。

**返回值:**该方法返回分区日期时间。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果结果超出支持的范围。

下面的程序说明了 Instant()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.ofInstant() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create Instant object
        Instant lt
            = Instant
                  .parse("2018-10-20T16:55:30.00Z");

        // create a ZonID
        ZoneId zone = ZoneId.of("Europe/Paris");

        // apply ofInstant method
        // of ZonedDateTime class
        ZonedDateTime zt = ZonedDateTime
                               .ofInstant(lt, zone);

        // print the result
        System.out.println("ZonedDateTime is "
                           + zt);
    }
}
```

**Output:**

```java
ZonedDateTime is 2018-10-20T18:55:30+02:00[Europe/Paris]

```
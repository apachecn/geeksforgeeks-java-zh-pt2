# Java 中的 ZonedDateTime ofStrict()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-of strict-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-ofstrict-method-in-java-with-examples/)

**ZonedDateTime** 类的**of Trict()**方法，用于创建 ZonedDateTime 实例，严格验证本地日期-时间、偏移量和区域标识的组合，其中所有三个本地日期-时间、区域偏移量和区域标识都作为参数传递。如果偏移量无效，将引发异常。
**语法:**

```java
public static ZonedDateTime ofStrict(LocalDateTime localDateTime,
                                     ZoneOffset offset,
                                     ZoneId zone)
```

**参数:**该方法接受三个参数**本地日期时间**为本地日期时间，**偏移**为区域偏移，**区域**为时区。
**返回值:**该方法返回分区日期时间。
下面的程序说明了 ofStrict()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ZonedDateTime.ofStrict() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create local date time object
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-01-29T23:55:59.00");

        // create ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(1);

        // create a ZonID
        ZoneId zone
            = ZoneId.of("Europe/Paris");

        // apply ofStrict method
        // of ZonedDateTime class
        ZonedDateTime zt
            = ZonedDateTime
                  .ofStrict(
                      ldt, zoneOffset, zone);

        // print the result
        System.out.println("ZonedDateTime is "
                           + zt);
    }
}
```

**Output:** 

```java
ZonedDateTime is 2019-01-29T23:55:59+01:00[Europe/Paris]
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ZonedDateTime.ofStrict() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create local date-time object
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-01-29T23:55:59.00");

        // create ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(0);

        // create a ZonID
        ZoneId zone = ZoneId.of("UTC");

        // apply ofStrict method
        // of ZonedDateTime class
        ZonedDateTime zt
            = ZonedDateTime
                  .ofStrict(
                      ldt, zoneOffset, zone);

        // print the result
        System.out.println("ZonedDateTime is "
                           + zt);
    }
}
```

**Output:** 

```java
ZonedDateTime is 2019-01-29T23:55:59Z[UTC]
```

**参考资料:**
[【https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddtetime . html # ofstrict(Java . time . localdatetime，java.time.ZoneOffset，java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#ofStrict(java.time.LocalDateTime, java.time.ZoneOffset, java.time.ZoneId))
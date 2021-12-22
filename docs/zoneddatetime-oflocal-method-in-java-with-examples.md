# Java 中 Local()方法的 ZonedDateTime 示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-of local-in-Java-method-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-oflocal-method-in-java-with-examples/)

**ofLocal()** 一个**ZONADDATETime**类的方法，用于使用 ZonmeId 和首选偏移量(如果可能)从本地日期时间创建 ZONADDATETime 的实例，其中所有三个本地日期时间、区域偏移量和区域 Id 都作为参数传递。本地日期时间被解析为时间线上的单个时刻，这是通过为由区域标识的规则定义的本地日期时间找到从世界协调时/格林威治时间的有效偏移来实现的。

**语法:**

```
public static ZonedDateTime ofLocal(LocalDateTime localDateTime,
                                    ZoneId zone,
                                    ZoneOffset preferredOffset)

```

**参数:**该方法接受三个参数**即时**为本地日期时间，**区域**为时区，**区域偏移**为区域偏移。

**返回值:**该方法返回分区日期时间。

以下程序说明了本地()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.ofLocal() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create localDateTime object
        LocalDateTime lt
            = LocalDateTime
                  .parse("2019-01-29T23:55:59.00");

        // create ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(11);

        // create a ZonID
        ZoneId zone
            = ZoneId.of("Europe/Paris");

        // apply ofLocal method
        // of ZonedDateTime class
        ZonedDateTime zt
            = ZonedDateTime
                  .ofLocal(lt, zone, zoneOffset);

        // print the result
        System.out.println("ZonedDateTime is "
                           + zt);
    }
}
```

**Output:**

```
ZonedDateTime is 2019-01-29T23:55:59+01:00[Europe/Paris]

```

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.ofLocal() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create localDateTime object
        LocalDateTime lt
            = LocalDateTime
                  .parse("2019-01-29T23:55:59.00");

        // create ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(10);

        // create a ZonID
        ZoneId zone
            = ZoneId.of("Australia/Darwin");

        // apply ofLocal method
        // of ZonedDateTime class
        ZonedDateTime zt
            = ZonedDateTime
                  .ofLocal(lt, zone, zoneOffset);

        // print the result
        System.out.println("ZonedDateTime is "
                           + zt);
    }
}
```

**Output:**

```
ZonedDateTime is 2019-01-29T23:55:59+09:30[Australia/Darwin]

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddtetime . html # office constant(Java . time . localdatetime，java.time.ZoneOffset，java.time.ZoneId)】](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#ofInstant(java.time.LocalDateTime, java.time.ZoneOffset, java.time.ZoneId))
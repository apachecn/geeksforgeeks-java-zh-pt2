# 带区域的区域数据时间带示例的 Java 中的区域本地()方法

> 原文:[https://www . geeksforgeeks . org/zone ddatetime-with zone same local-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withzonesamelocal-method-in-java-with-examples/)

一个 **ZonedDateTime** 类的**witzonesamelopment()**方法，用于通过更改时区来返回这个 ZonedDateTime 对象的副本，如果可能的话，不更改本地日期时间。只有当本地日期时间对于新区域无效时，才会更改本地日期时间，这是使用与本地相同的方法(LocalDateTime、ZoneId、ZoneOffset)确定的。

**语法:**

```java
public ZonedDateTime withZoneSameLocal(ZoneId zone)

```

**参数:**此方法接受一个单参数**区域**时区更改为。它不应为空。

**返回值:**该方法根据请求区域的日期时间返回一个**区域日期时间**。

下面的程序说明了 withZoneSameLocal()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.withZoneSameLocal() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ZonedDateTime
        System.out.println("ZonedDateTime of Calcutta: "
                           + zonedDT);

        // apply withZoneSameLocal()
        ZonedDateTime zonedDT2
            = zonedDT.withZoneSameLocal(
                ZoneId.of("Pacific/Fiji"));

        // print ZonedDateTime after withZoneSameLocal()
        System.out.println("ZonedDateTime of Fuji: "
                           + zonedDT2);
    }
}
```

**Output:**

```java
ZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime of Fuji: 2018-12-06T19:21:12.123+13:00[Pacific/Fiji]

```

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.withZoneSameLocal() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print ZonedDateTime
        System.out.println("ZonedDateTime of Calcutta: "
                           + zonedDT);

        // apply withZoneSameLocal()
        ZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameLocal(
                      ZoneId.of("Canada/Yukon"));

        // print ZonedDateTime after withZoneSameLocal()
        System.out.println("ZonedDateTime of yukon: "
                           + zonedDT2);
    }
}
```

**Output:**

```java
ZonedDateTime of Calcutta: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ZonedDateTime of yukon: 2018-10-25T23:12:31.123-07:00[Canada/Yukon]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # withouzonesamelocal(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#withZoneSameLocal(java.time.ZoneId))
# Java 中的 ZoneId from()方法，示例

> 原文:[https://www . geesforgeks . org/zoneid-from-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-from-method-in-java-with-examples/)

**ZoneId** 类的 **from()** 方法用于从作为参数传递的临时进程对象获取 ZoneId 的实例。此方法基于表示任意一组日期和时间信息的临时进程获取一个区域，此方法将其转换为区域标识的实例。

**语法:**

```java
public static ZoneId from(TemporalAccessor temporal)

```

**参数:**该方法接受单个参数**时态**，表示要转换的时态对象，不能为空。

**返回值:**该方法返回**区域标识**，不能为空。

**异常:**如果该方法无法将时态转换为区域标识，则该方法将抛出**日期时间异常**。

以下程序说明了 from()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZoneId.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create TemporalAccessor object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse("2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // get ZoneId from this TemporalAccessor
        ZoneId response = ZoneId.from(zoneddatetime);

        // print result
        System.out.println("Zone Id got from "
                           + "TemporalAccessor object \n"
                           + zoneddatetime + "\nis " + response);
    }
}
```

**Output:**

```java
Zone Id got from TemporalAccessor object 
2018-10-25T23:12:31.123+02:00[Europe/Paris]
is Europe/Paris

```

**程序 2:**

```java
// Java program to demonstrate
// ZoneId.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create TemporalAccessor object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.now();

        // get ZoneId from this TemporalAccessor
        ZoneId response = ZoneId.from(zoneddatetime);

        // print result
        System.out.println("Zone Id got from "
                           + "TemporalAccessor object \n"
                           + zoneddatetime + "\nis " + response);
    }
}
```

**Output:**

```java
Zone Id got from TemporalAccessor object 
2018-12-10T18:20:03.637Z[Etc/UTC]
is Etc/UTC

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # from(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#from(java.lang.Object))
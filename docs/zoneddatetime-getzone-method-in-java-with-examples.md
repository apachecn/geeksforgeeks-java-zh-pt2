# Java 中的 ZonedDateTime getZone()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getzone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getzone-method-in-java-with-examples/)

一个**时区**类的 **getZone()** 方法用于从这个时区获取时区。此方法返回区域标识，如“亚洲/加尔各答”。

**语法:**

```java
public ZoneId getZone()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个代表时区的**区域标识**。

下面的程序说明了 getZone()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.getZone() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get zone
        ZoneId value = zoneddatetime.getZone();

        // print result
        System.out.println("Time Zone:" + value);
    }
}
```

**输出:**

```java
Time Zone:Asia/Calcutta

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.getZone() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get zone
        ZoneId value = zoneddatetime.getZone();

        // print result
        System.out.println("Time Zone:" + value);
    }
}
```

**输出:**

```java
Time Zone:Europe/Paris

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getZone()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getZone())
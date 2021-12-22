# zoneddatime now()Java 中的方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-now-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有三种 now()方法。

### 现在()

**now()** 一个 **ZonedDateTime** 类的方法，用于从默认时区的系统时钟中获取当前日期时间。此方法将根据系统时钟返回 ZonedDateTime，并使用默认时区来获取当前日期时间。时区和偏移量将根据时钟中的时区进行设置。

**语法:**

```java
public static ZonedDateTime now()

```

**参数:**该方法不接受参数。

**返回值:**此方法使用系统时钟返回当前日期时间。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ZonedDateTime object
        ZonedDateTime lt
            = ZonedDateTime.now();

        // print result
        System.out.println("ZonedDateTime : "
                           + lt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2019-01-21T05:36:18.973Z[Etc/UTC]

```

### 现在(时钟)

**now(Clock clock)** 一个 **ZonedDateTime** 类的方法，用于根据作为参数传递的指定时钟返回当前日期时间。时区和偏移量将根据时钟中的时区进行设置。

**语法:**

```java
public static ZonedDateTime now(Clock clock)

```

**参数:**该方法接受**时钟**作为参数，该参数是要使用的时钟。

**返回值:**此方法返回**当前日期时间**。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        Clock cl = Clock.systemUTC();

        // create an ZonedDateTime object using now(Clock)
        ZonedDateTime lt
            = ZonedDateTime.now(cl);

        // print result
        System.out.println("ZonedDateTime : "
                           + lt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2019-01-21T05:36:25.966Z

```

### 现在(区域标识区域)

**now(ZoneId zone)** 一个 **ZonedDateTime** 类的方法，用于从指定时区的系统时钟返回作为参数传递的当前日期时间。指定时区避免了对默认时区的依赖。偏移量将从指定的时区开始计算。

**语法:**

```java
public static ZonedDateTime now(ZoneId zone)

```

**参数:**该方法接受**区域**作为参数，该参数是要使用的区域。

**返回值:**此方法返回**当前日期时间**。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        ZoneId zid = ZoneId.of("Europe/Paris");

        // create an ZonedDateTime object using now(zoneId)
        ZonedDateTime lt
            = ZonedDateTime.now(zid);

        // print result
        System.out.println("ZonedDateTime : "
                           + lt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2019-01-21T06:36:30.188+01:00[Europe/Paris]

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#now())
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#now(java.time.Clock))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/time](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#now(java.time.ZoneId))
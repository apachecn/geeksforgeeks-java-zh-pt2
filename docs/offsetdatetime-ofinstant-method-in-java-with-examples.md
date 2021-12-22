# Java 中的 OffsetDateTime ofInstant()方法，示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-of instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-ofinstant-method-in-java-with-examples/)

Java 中 **OffsetDateTime** 类的 **ofInstant(Instant instant，ZoneId ZoneId)**方法用于从指定的 Instant 和 ZoneId 创建 **OffsetDateTime** 的实例。由于在世界协调时/格林威治时间中，每个时刻只有一个有效的偏移，因此从后者导出偏移很简单。

**语法:**

```
public static OffsetDateTime
       ofInstant(Instant instant,
                 ZoneId zone)

```

**参数:**该方法接受两个参数:

*   **instant**–它属于 Instant 类型，表示创建 offsetdatetime 的瞬间。它不应为空。
*   **区域**–属于区域标识类型，代表当时的区域。它不应为空。

**返回值:**该方法返回根据指定参数创建的**偏移日期时间**。

**异常:**如果结果超出支持范围，该方法抛出**日期时间异常**。

下面的程序说明了 Java 中 OffsetDateTime 类的 ofInstant()方法:

**程序 1:**

```
// Java program to demonstrate
// OffsetDateTime ofInstant() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print date-time
        System.out.println("DATE-TIME: "
                           + offsetdatetime);
    }
}
```

**Output:**

```
DATE-TIME: 2020-05-20T04:05:38.471Z

```

**程序 2:**

```
// Java program to demonstrate
// OffsetDateTime ofInstant() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create Instant object
        Instant instant = Instant.now(
            Clock.systemUTC());

        // Create ZoneId object
        ZoneId zone = ZoneId.of("Z");

        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.ofInstant(
                instant,
                zone);

        // Print date-time
        System.out.println("DATE-TIME: "
                           + offsetdatetime);
    }
}
```

**Output:**

```
DATE-TIME: 2020-05-20T04:05:42.166Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # of instant(Java . time . instant，java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#ofInstant(java.time.Instant, java.time.ZoneId))
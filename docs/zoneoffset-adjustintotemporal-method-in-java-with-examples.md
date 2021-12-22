# Java 中的区域偏移调整(时态)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-adjustintemporal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-adjustintotemporal-method-in-java-with-examples/)

使用 **java.time 包**中 **ZoneOffset 类**的**adjusttinto(Temporal)**方法获取一个调整后的 Temporal 实例，并将该 ZoneOffset 实例调整到其中。该方法以时态实例为参数，返回一个时态实例，即调整后的实例。

**语法:**

```java
public Temporal adjustInto(Temporal temporalInstance)

```

**参数:**该方法接受一个参数**临时实例**，它是要调整的临时实例。

**返回值:**这个方法返回一个**时态实例**，它是这个时态实例的调整值。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** : If adjustment cannot be made.
*   **Arithmetic exception** : If there is a numerical overflow.

以下示例说明了 ZoneOffset.adjustInto()方法:

**例 1:**

```java
// Java code to illustrate adjustInto() method

import java.time.temporal.*;
import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the Temporal instance
        ZonedDateTime temporalInstance
            = ZonedDateTime.now();

        System.out.println("Original Temporal instance: "
                           + temporalInstance);

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);

        // Using adjustInto() method
        ZonedDateTime adjustedTemporal
            = (ZonedDateTime)zoneOffset
                  .adjustInto(temporalInstance);

        System.out.println("Adjusted Temporal instance: "
                           + adjustedTemporal);
    }
}
```

**输出:**

```java
Original Temporal instance: 2018-12-11T09:44:14.373Z[Etc/UTC]
Adjusted Temporal instance: 2018-12-11T09:44:14.373Z[Etc/UTC]

```

**例 2:**

```java
// Java code to illustrate adjustInto() method

import java.time.temporal.*;
import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the Temporal instance
        OffsetDateTime temporalInstance
            = OffsetDateTime.now();

        System.out.println("Original Temporal instance: "
                           + temporalInstance);

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);

        // Using adjustInto() method
        Temporal adjustedTemporal
            = zoneOffset
                  .adjustInto(temporalInstance);

        System.out.println("Adjusted Temporal instance: "
                           + adjustedTemporal);
    }
}
```

**输出:**

```java
Original Temporal instance: 2018-12-11T09:44:16.893Z
Adjusted Temporal instance: 2018-12-11T09:44:16.893+05:00

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#adjustInto-java.time.temporal.Temporal-)
# Java 中的 OffsetTime adjustInto()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-adjustin to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-adjustinto-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**adjustitinto()**方法将指定的时态对象调整为与该对象具有相同的时间。

**语法:**

```
public Temporal adjustInto(Temporal temporal)

```

**参数:**该方法接受单个参数**时态**，指定要调整的目标对象，不为空。

**返回值:**返回调整后的对象，不为空

**错误和异常:**此方法抛出如下所述的两个异常:

*   **datetimeexception** : If adjustment is not possible.
*   **Arithmetic exception** : If there is a numerical overflow.

以下程序说明了 adjustInto()方法:

**程序 1 :**

```
// Java program to demonstrate the adjustInto() method

import java.time.OffsetTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Current time
        ZonedDateTime date = ZonedDateTime.now();

        // Prints the current time
        System.out.println("Current date:" + date);

        // Parsed the date
        OffsetTime date1 = OffsetTime.parse("14:30:30+05:00");

        // Adjusts
        date = (ZonedDateTime)date1.adjustInto(date);
        System.out.println("Adjusted date:" + date);
    }
}
```

**输出:**

```
Current date:2018-12-11T10:01:37.877Z[Etc/UTC]
Adjusted date:2018-12-11T14:30:30Z[Etc/UTC]

```

**程序二** :

```
// Java program to demonstrate the adjustInto()
// method exceptions

import java.time.OffsetTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // Current time
            // Current time
            ZonedDateTime date = ZonedDateTime.now();

            // Prints the current time
            System.out.println("Current date:" + date);

            // Parsed the date
            OffsetTime date1 = OffsetTime.parse("25:30:30+05:00");

            // Adjusts
            date = (ZonedDateTime)date1.adjustInto(date);
            System.out.println("Adjusted date:" + date);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Current date:2018-12-11T10:01:42.520Z[Etc/UTC]
java.time.format.DateTimeParseException: Text '25:30:30+05:00' could not be parsed: Invalid value for HourOfDay (valid values 0 - 23): 25

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # adjustInto-Java . time . temporal-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#adjustInto-java.time.temporal.Temporal-)
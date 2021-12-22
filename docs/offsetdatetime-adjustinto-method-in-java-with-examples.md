# Java 中的 OffsetDateTime adjustInto()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-adjustint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-adjustinto-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**adjustitinto()**方法将指定的时态对象调整为与该对象具有相同的日期和时间。

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

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Current time
        ZonedDateTime date = ZonedDateTime.now();

        // Prints the current date
        System.out.println("Current date is: " + date);

        // Parses the date
        OffsetDateTime date1 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // Function used
        date = (ZonedDateTime)date1.adjustInto(date);

        // Prints the date
        System.out.println(date);
    }
}
```

**输出:**

```
Current date is: 2018-12-11T09:53:15.294Z[Etc/UTC]
2018-12-12T13:30:30Z[Etc/UTC]

```

**程序二** :

```
// Java program to demonstrate the adjustInto() method
// exceptions

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // Current time
            ZonedDateTime date = ZonedDateTime.now();

            // Prints the current date
            System.out.println("Current date is: " + date);

            // Parses the date
            OffsetDateTime date1 = OffsetDateTime.parse("2018-13-12T13:30:30+05:00");

            // Function used
            date = (ZonedDateTime)date1.adjustInto(date);

            // Prints the date
            System.out.println(date);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Current date is: 2018-12-11T09:53:24.660Z[Etc/UTC]
java.time.format.DateTimeParseException: Text '2018-13-12T13:30:30+05:00' could not be parsed: Invalid value for MonthOfYear (valid values 1 - 12): 13

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/temporal adjuster . html](https://docs.oracle.com/javase/8/docs/api/java/time/temporal/TemporalAdjuster.html)
# OffsetDateTime now()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-now-method-in-Java-with-example/](https://www.geeksforgeeks.org/offsetdatetime-now-method-in-java-with-example/)

1.  The **now()** method of the **OffsetDateTime** class in Java is used to obtain the current offset date-time using the system clock. This is done after querying the system clock in the default time zone. The method uses the hardcoded clock for testing instead of the alternative clock.

    **语法:**

    ```
    public static OffsetDateTime now()
    ```

    **参数:**该方法不接受任何参数。

    **返回值:**该方法使用系统时钟返回当前**偏移日期时间**。它不返回空值。

    **异常:**此方法不抛出任何异常。

    下面的程序说明了 Java 中 OffsetDateTime 类的 now()方法:
    **程序:**

    ```
    // Java program to demonstrate
    // OffsetDateTime now() method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create OffsetDateTime object
            OffsetDateTime offsetdatetime
                = OffsetDateTime.now();

            // Print date-time
            System.out.println(
                "DATE-TIME: "
                + offsetdatetime);
        }
    }
    ```

    **Output:**

    ```
    DATE-TIME: 2020-05-20T05:40:08.721Z

    ```

2.  The **now(Clock clock)** method of the **OffsetDateTime** class in Java is used to get the current date-time using a specified clock. This is done after querying the specified clock while the offset is calculated using the timezone in the clock. As already specified this method can use an alternative clock, unlike the previously mentioned now() method.

    **语法:**

    ```
    public static OffsetDateTime now(Clock clock)

    ```

    **参数:**该方法接受时钟类型的**时钟**，用于获取所需的日期时间。

    **返回值:**该方法使用指定的时钟返回当前**偏移日期时间**。

    **异常:**此方法不抛出任何异常。

    下面的程序说明了 Java 中 OffsetDateTime 类的 now(时钟时钟)方法:

    **程序:**

    ```
    // Java program to demonstrate
    // OffsetDateTime now(Clock clock) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create OffsetDateTime object
            OffsetDateTime offsetdatetime
                = OffsetDateTime.now(
                    Clock.systemUTC());

            // Print date-time
            System.out.println(
                "DATE-TIME: "
                + offsetdatetime);
        }
    }
    ```

    **Output:**

    ```
    DATE-TIME: 2020-05-20T13:12:18.825Z

    ```

3.  The **now(ZoneId zone)** method of the **OffsetDateTime** class in Java is used to obtain the current date-time by using the system clock in the specified time zone. This is done after querying the system clock in the specified time zone. The method uses the hardcoded clock for testing instead of the alternative clock.

    **语法:**

    ```
    public static OffsetDateTime now(ZoneId zone)

    ```

    **参数:**该方法接受**区**作为参数。它用于获取日期时间。

    **返回值:**此方法使用指定时区的系统时钟返回当前**偏移日期时间**。

    **异常:**此方法不抛出任何异常。

    下面的程序说明了 Java 中 OffsetDateTime 类的 now(ZoneID zone)方法:

    **程序:**

    ```
    // Java program to demonstrate
    // OffsetDateTime now(ZoneId zone) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create OffsetDateTime object
            OffsetDateTime offsetdatetime
                = OffsetDateTime.now(
                    ZoneId.systemDefault());

            // Print date-time
            System.out.println(
                "DATE-TIME: "
                + offsetdatetime);
        }
    }
    ```

    **Output:**

    ```
    DATE-TIME: 2020-05-20T13:12:40.458Z

    ```

**参考文献:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#now())
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#now(java.time.Clock))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # now(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#now(java.time.ZoneId))
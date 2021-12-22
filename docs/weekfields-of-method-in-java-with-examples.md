# Java 中()方法的 WeekFields 示例

> 原文:[https://www . geesforgeks . org/weekfields-of-in-Java-method-in-with-examples/](https://www.geeksforgeeks.org/weekfields-of-method-in-java-with-examples/)

**周域类**的()方法的**帮助我们获取一个周域的实例。**

根据传递给它的参数，有两种类型的()方法。

1.  **of(DayOfWeek firstDayOfWeek, int minimalDaysInFirstWeek)**: This method helps us to an instance of WeekFields from the first day-of-week and minimal days.WeekFields instances are singletons; for each unique combination of firstDayOfWeek and minimalDaysInFirstWeek the same instance will be returned.

    **语法:**

    ```
    public static WeekFields of(DayOfWeek firstDayOfWeek, 
                              int minimalDaysInFirstWeek)

    ```

    **参数:**该方法接受两个参数:

    *   **第一天第一周**是一周的第一天。它不应该为空
    *   **最小天数第一周**是第一周的最小天数，从 1 到 7。

    **返回值:**该方法返回周定义，不为空。

    **异常:**如果最小日的值小于 1 或大于 7，该方法抛出 **IllegalArgumentException** 。

    下面的程序说明了 weekfield . of(DayOfWeek first DayOfWeek，int minimalDaysInFirstWeek)方法:
    **程序 1:**

    ```
    // Java program to demonstrate
    // WeekFields.of(DayOfWeek, int) method

    import java.time.DayOfWeek;
    import java.time.temporal.WeekFields;

    public class GFG {
        public static void main(String[] args)
        {

            // create WeekFields
            WeekFields weekFields
                = WeekFields.of(DayOfWeek.MONDAY, 1);

            // print results
            System.out.println(weekFields);
        }
    }
    ```

    **Output:**

    ```
    WeekFields[MONDAY, 1]

    ```

2.  **of(Locale locale)**: This method help us to get an instance of WeekFields appropriate for a locale.
    **Syntax:**

    ```
    public static WeekFields of(Locale locale)

    ```

    **参数:**该方法接受**地区**作为参数，该参数是要使用的地区。它不应为空。

    **返回值:**该方法返回周定义，不为空。

    下面的程序说明了 WeekFields.of(龙敏，长最大最小值，长最大值)方法:
    **程序 2:**

    ```
    // Java program to demonstrate
    // of(Locale locale) method

    import java.time.temporal.WeekFields;
    import java.util.Locale;

    public class GFG {
        public static void main(String[] args)
        {

            Locale locale = new Locale("EN", "US");

            // create WeekFields
            WeekFields weekFields = WeekFields.of(locale);

            // print results
            System.out.println(weekFields);
        }
    }
    ```

    **Output:**

    ```
    WeekFields[SUNDAY, 1]

    ```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html)
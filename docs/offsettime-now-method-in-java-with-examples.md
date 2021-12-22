# OffsetTime now()方法在 Java 中用示例

> 原文:[https://www . geeksforgeeks . org/offsettime-now-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-now-method-in-java-with-examples/)

1.  The **now()** method of OffsetTime class in Java obtains the current time from the system clock in the default time-zone.

    **语法:**

    ```
    public static OffsetTime now()

    ```

    **参数:**该方法不接受任何参数。

    **返回值:**使用系统时钟和默认时区返回当前时间，不为空。

    下面的程序说明了 now()方法:

    **程序 1 :**

    ```
    // Java program to demonstrate the now() method

    import java.time.OffsetTime;

    public class GFG {
        public static void main(String[] args)
        {
            // Parses the time
            OffsetTime time = OffsetTime.now();

            // Prints the current time
            System.out.println("Current time: " + time);
        }
    }
    ```

    **Output:**

    ```
    Current time: 02:58:01.700Z

    ```

2.  The **now(clock)** method of OffsetTime class in Java obtains the current time from the specified clock in the parameter.

    **语法:**

    ```
    public static OffsetTime now(Clock clock)

    ```

    **参数:**此方法接受单个参数**时钟**，指定要使用的时钟且不为空。

    **返回值:**返回当前时间，不为空。

    下面的程序说明了 now(时钟)方法:

    **程序 1 :**

    ```
    // Java program to demonstrate the now(clock) method

    import java.time.OffsetTime;
    import java.time.Clock;

    public class GFG {
        public static void main(String[] args)
        {
            // Parses the time
            OffsetTime time = OffsetTime.now();

            // Prints the current time
            System.out.println("Current time: " + Clock.systemUTC());
        }
    }
    ```

    **Output:**

    ```
    Current time: SystemClock[Z]

    ```
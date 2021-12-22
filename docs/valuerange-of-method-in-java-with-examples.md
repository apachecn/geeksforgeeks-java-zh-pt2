# Java 中()方法的值范围，示例

> 原文:[https://www . geesforgeks . org/value range-of-in-Java-method-with-examples/](https://www.geeksforgeeks.org/valuerange-of-method-in-java-with-examples/)

**值范围类**的()方法的**帮助我们根据传递给它的参数获取值范围。**

根据传递给它的参数，有三种类型的()方法。

1.  **of(long min, long max)**: This method help us to get a fixed value range where the minimum and maximum values are fixed.
    **Syntax:**

    ```
    public static ValueRange of(long min, long max)

    ```

    **参数:**该方法接受两个参数:

    *   **分钟**是最小值
    *   **最大值**即最大值

    **返回值:**此方法返回最小值、最大值的值范围，不为空。

    **异常:**如果最小值大于最大值，该方法抛出 **IllegalArgumentException** 。

    下面的程序说明了 ValueRange.of(龙敏，long max)方法:
    **程序 1:**

    ```
    // Java program to demonstrate
    // ValueRange.of(long min, long max) method

    import java.time.temporal.ValueRange;

    public class GFG {
        public static void main(String[] args)
        {

            // create ValueRange using
            // of(long min, long max)
            ValueRange vRange = ValueRange.of(0, 66666);

            // print results
            System.out.println("ValueRange: "
                               + vRange.toString());
        }
    }
    ```

    **Output:**

    ```
    ValueRange: 0 - 66666

    ```

2.  **of(long min, long maxSmallest, long maxLargest)**: This method helps us to get a variable value range where the minimum value is fixed and the maximum value may vary.

    **语法:**

    ```
    public static ValueRange of(long min,
                                long maxSmallest,
                                long maxLargest)

    ```

    **参数:**该方法接受三个参数:

    *   **min** 为最小值，
    *   **最大最小值**哪个是最小最大值
    *   **最大**是最大的最大值。

    **返回值:**该方法返回最小值、最小最大值、最大值的取值范围，不为空。

    **异常:**如果最小值大于最小最大值，或者最小最大值大于最大值，该方法抛出 **IllegalArgumentException** 。

    下面的程序说明了 ValueRange.of(龙敏，长最大最小值，长最大值)的方法:
    **程序 2:**

    ```
    // Java program to demonstrate
    // of(long, long, long) method

    import java.time.temporal.ValueRange;

    public class GFG {
        public static void main(String[] args)
        {

            // create ValueRange using
            // of(long min, long maxSmallest, long maxLargest)
            ValueRange vRange = ValueRange.of(0, 230, 500);

            // print results
            System.out.println("ValueRange: "
                               + vRange.toString());
        }
    }
    ```

    **Output:**

    ```
    ValueRange: 0 - 230/500

    ```

3.  **of(long minSmallest, long minLargest, long maxSmallest, long maxLargest)**: This method helps us to get a fully variable value range where both the minimum and maximum value may vary.

    **语法:**

    ```
    public static ValueRange of(long minSmallest, long minLargest,
                                long maxSmallest, long maxLargest)

    ```

    **参数:**该方法接受四个参数:

    *   **最小最小值是哪个最小**
    *   **最小最大**即最大最小值，
    *   **最大最小值**哪个是最小最大值
    *   **最大**是最大的最大值。

    **返回值:**该方法返回最小值、最大值、最小值、最大值、最大值的取值范围，不为空。

    **异常:**如果最小的最小值大于最小的最大值，或者最小的最大值大于最大的最大值，或者最大的最小值大于最大的最大值，这个方法抛出 **IllegalArgumentException** 。

    下面的程序说明了 ValueRange.of(long minSmallest，long minmaxmaximum，long maxminism，long maxmaxmaxmaxmaxmaximum)方法:
    **程序 2:**

    ```
    // Java program to demonstrate
    // of(long, long, long, long) method

    import java.time.temporal.ValueRange;

    public class GFG {
        public static void main(String[] args)
        {

            // create ValueRange using
            // of(long minSmallest, long minLargest,
            // long maxSmallest, long maxLargest)
            ValueRange vRange
                = ValueRange.of(0, 1, 500, 1000);

            // print results
            System.out.println("ValueRange: "
                               + vRange.toString());
        }
    }
    ```

    **Output:**

    ```
    ValueRange: 0/1 - 500/1000

    ```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html)
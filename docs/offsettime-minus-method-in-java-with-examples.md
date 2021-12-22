# Java 中的 OffsetTime 减()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-减去-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-minus-method-in-java-with-examples/)

1.  The **minus(amountToSubtract, unit)** method of OffsetTime class in Java returns a copy of this time with the specified amount subtracted.

    **语法:**

    ```java
    public OffsetTime minus(long amountToSubtract, TemporalUnit unit)

    ```

    **参数:**该方法接受两个参数，描述如下:

    *   **amountToSubtract** :是一个强制参数，指定从结果中减去的单位数量，可以是负数。
    *   **单位**:是强制参数，指定要减去的金额单位，不为空。

    **返回值:**根据这个时间返回一个偏移量，减去指定的量，不为空

    下面的程序说明了减()方法:

    **程序 1 :**

    ```java
    // Java program to demonstrate the minus() method

    import java.time.OffsetTime;
    import java.time.temporal.ChronoUnit;

    public class GFG {
        public static void main(String[] args)
        {
            // Parses the time
            OffsetTime time = OffsetTime.parse("11:35:40+06:03");
            System.out.println("Time after subtraction of hours: " 
                               + time.minus(2, ChronoUnit.HOURS));
        }
    }
    ```

    **Output:**

    ```java
    Time after subtraction of hours: 09:35:40+06:03

    ```

    **程序 2** :

    ```java
    // Java program to demonstrate the minus() method

    import java.time.OffsetTime;
    import java.time.temporal.ChronoUnit;

    public class GFG {
        public static void main(String[] args)
        {
            // Parses the time
            OffsetTime time = OffsetTime.parse("11:35:40+06:03");
            System.out.println("Time after subtraction of minutes: " 
                               + time.minus(2, ChronoUnit.MINUTES));
        }
    }
    ```

    **Output:**

    ```java
    Time after subtraction of minutes: 11:33:40+06:03

    ```

2.  The **minus(amountToSubtract)** method of OffsetTime class in Java returns a copy of this time with the specified amount subtracted.

    **语法:**

    ```java
    public OffsetTime minus(TemporalAmount amountToSubtract)

    ```

    **参数:**该方法接受单个参数 **amountToSubtract** ，指定要减去的金额，不为空。

    **返回值:**根据这个时间，做减法，返回一个偏移量，不为空。

    **错误和异常:**程序返回两个异常，描述如下:

    *   **DateTimeException:** 不能做减法就抛出。
    *   **算术异常:**如果出现数值溢出，则抛出。

    下面的程序说明了减()方法:

    **程序 1 :**

    ```java
    // Java program to demonstrate the minus() method

    import java.time.Duration;
    import java.time.OffsetTime;

    public class GFG {
        public static void main(String[] args)
        {
            // Parses the time
            OffsetTime time = OffsetTime.parse("11:35:40+06:03");
            System.out.println("Time after subtraction of hours: " 
                                + time.minus(Duration.ofHours(2)));
        }
    }
    ```

    **Output:**

    ```java
    Time after subtraction of hours: 09:35:40+06:03

    ```

    **程序 2** :

    ```java
    // Java program to demonstrate the minus() method

    import java.time.Duration;
    import java.time.OffsetTime;

    public class GFG {
        public static void main(String[] args)
        {
            // Parses the time
            OffsetTime time = OffsetTime.parse("11:35:40+06:03");
            System.out.println("Time after subtraction of hours: " 
                              + time.minus(Duration.ofMinutes(28)));
        }
    }
    ```

    **Output:**

    ```java
    Time after subtraction of hours: 11:07:40+06:03

    ```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html #减-long-Java . time . temporalunit-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#minus-long-java.time.temporal.TemporalUnit-)
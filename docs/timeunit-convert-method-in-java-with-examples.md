# Java 中的 TimeUnit convert()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-convert-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-convert-method-in-java-with-examples/)

**时间单位类**的 **convert()** 方法用于将给定单位的给定持续时间转换为该单位。由于转换涉及从较大到较小或从较小到较大的单位，因此在使用这种方法时会出现精度损失和溢出。

**语法:**

```java
public long convert(long sourceDuration, 
                        TimeUnit sourceUnit)
```

**参数:**该方法接受两个强制参数:

*   **源持续时间**–给定源单位的持续时间
*   **源单位**–源持续时间参数的单位

**返回值:**此方法返回本单位的**换算时长**，或龙。如果转换会负溢出，则为最小值，否则为长值。最大值，如果它肯定会溢出。

下面的程序说明了 TimeUnit convert()方法的实现:

**程序 1:** 将分钟转换为毫秒

```java
// Java program to demonstrate
// convert() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get time to be converted in Minutes
        long timeInMinutes = 55L;

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert Minutes to milliseconds
        // using convert() method
        System.out.println("Time " + timeInMinutes
                           + " minutes in milliSeconds = "
                           + time.convert(timeInMinutes,
                                          TimeUnit.MINUTES));
    }
}
```

**Output:**

```java
Time 55 minutes in milliSeconds = 3300000

```

**程序 2:** 将秒转换为分钟

```java
// Java program to demonstrate
// convert() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get time to be converted in Seconds
        long timeInSec = 300L;

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MINUTES;

        // Convert Seconds to Minutes
        // using convert() method
        System.out.println("Time " + timeInSec
                           + " seconds in minutes = "
                           + time.convert(timeInSec,
                                          TimeUnit.SECONDS));
    }
}
```

**Output:**

```java
Time 300 seconds in minutes = 5

```
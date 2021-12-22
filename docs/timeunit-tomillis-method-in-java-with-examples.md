# Java 中的 TimeUnit toMillis()方法，带示例

> 原文:[https://www . geesforgeks . org/time unit-tomi llis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-tomillis-method-in-java-with-examples/)

**时间单位类**的**Tomilis()**方法用于获取从 1970 年 1 月 1 日午夜协调世界时开始，由时间单位对象表示的时间，以秒为单位。

**语法:**

```
public long toMillis(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。

**返回值:**该方法将**转换后的时长**返回为秒。

下面的程序说明了 TimeUnit toMillis()方法的实现:

**程序 1:**

```
// Java program to demonstrate
// toMillis() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in seconds
        long timeInSec = (new Date().getTime()) / 1000;

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.SECONDS;

        // Convert seconds to milliSeconds
        // using toMillis() method
        System.out.println("Time " + timeInSec
                           + " Seconds in MilliSeconds = "
                           + time.toMillis(timeInSec));
    }
}
```

**Output:**

```
Time 1539585757 Seconds in MilliSeconds = 1539585757000

```

**程序 2:**

```
// Java program to demonstrate
// toMillis() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Calendar;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInSec = (Calendar
                              .getInstance()
                              .getTimeInMillis())
                         / 1000;

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.SECONDS;

        // Convert seconds to milliSeconds
        // using toMillis() method
        System.out.println("Time " + timeInSec
                           + " Seconds in MilliSeconds = "
                           + time.toMillis(timeInSec));
    }
}
```

**Output:**

```
Time 1539585759 Seconds in MilliSeconds = 1539585759000

```
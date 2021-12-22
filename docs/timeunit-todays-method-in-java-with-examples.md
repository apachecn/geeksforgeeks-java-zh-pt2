# Java 中的 TimeUnit toDays()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-today-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-todays-method-in-java-with-examples/)

**时间单位类**的**Today()**方法用于获取从 1970 年 1 月 1 日午夜协调世界时开始，由时间单位对象表示的时间，如天数。它相当于 DAYS.convert(duration，this)。

**语法:**

```
public long toDays(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。

**返回值:**该方法将**转换后的时长**返回为天数。

下面的程序说明了 TimeUnit toDays()方法的实现:

**程序 1:**

```
// Java program to demonstrate
// toDays() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = new Date().getTime();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to days
        // using toDays() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Days = "
                           + time.toDays(timeInMilliSec));
    }
}
```

**Output:**

```
Time 1539585725051 milliSeconds in Days = 17819

```

**程序 2:**

```
// Java program to demonstrate
// toDays() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Calendar;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = Calendar
                                  .getInstance()
                                  .getTimeInMillis();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to days
        // using toDays() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Days = "
                           + time.toDays(timeInMilliSec));
    }
}
```

**Output:**

```
Time 1539585730178 milliSeconds in Days = 17819

```
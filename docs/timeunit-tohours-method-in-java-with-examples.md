# Java 中的 TimeUnit toHours()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-to-hour-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-tohours-method-in-java-with-examples/)

**时间单位类**的**to hour()**方法用于获取时间单位对象表示的时间，以小时数表示，自 1970 年 1 月 1 日午夜 UTC 开始。

**语法:**

```
public long toHours(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。

**返回值:**该方法将**转换后的时长**返回为小时。

下面的程序说明了 TimeUnit toHours()方法的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toHours() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = new Date().getTime();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to Hours
        // using toHours() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Hours = "
                           + time.toHours(timeInMilliSec));
    }
}
```

**Output:**

```
Time 1539585595812 milliSeconds in Hours = 427662

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toHours() method of TimeUnit Class

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

        // Convert milliseconds to Hours
        // using toHours() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Hours = "
                           + time.toHours(timeInMilliSec));
    }
}
```

**Output:**

```
Time 1539585598692 milliSeconds in Hours = 427662

```
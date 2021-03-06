# Java 中的 TimeUnit toNanos()方法，带示例

> 原文:[https://www . geesforgeks . org/time unit-tonanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-tonanos-method-in-java-with-examples/)

**时间单位类**的 **toNanos()** 方法用于获取从 1970 年 1 月 1 日午夜协调世界时开始，由时间单位对象表示的时间，以纳秒数表示。
**语法:**

```java
public long toNanos(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。
**返回值:**该方法将**转换后的时长**返回为纳秒。
下面的程序说明了 TimeUnit toNanos()方法的实现:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toNanos() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = new Date().getTime();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to NanoSeconds
        // using toNanos() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in NanoSeconds = "
                           + time.toNanos(timeInMilliSec));
    }
}
```

**Output:** 

```java
Time 1539585501608 milliSeconds in NanoSeconds = 1539585501608000000
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toNanos() method of TimeUnit Class

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

        // Convert milliseconds to NanoSeconds
        // using toNanos() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in NanoSeconds = "
                           + time.toNanos(timeInMilliSec));
    }
}
```

**Output:** 

```java
Time 1539585503771 milliSeconds in NanoSeconds = 1539585503771000000
```
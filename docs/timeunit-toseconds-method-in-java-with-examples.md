# Java 中的 TimeUnit toSeconds()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-to seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-toseconds-method-in-java-with-examples/)

**时间单位类**的**至**方法用于获取从 1970 年 1 月 1 日午夜世界协调时开始，由时间单位对象表示的时间，以秒为单位。

**语法:**

```java
public long toSeconds(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。

**返回值:**该方法将**转换后的时长**返回为秒。

下面的程序说明了 TimeUnit toSeconds()方法的实现:

**程序 1:**

```java
// Java program to demonstrate
// toSeconds() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = new Date().getTime();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to Seconds
        // using toSeconds() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Seconds = "
                           + time.toSeconds(timeInMilliSec));
    }
}
```

**Output:**

```java
Time 1539585656193 milliSeconds in Seconds = 1539585656

```

**程序 2:**

```java
// Java program to demonstrate
// toSeconds() method of TimeUnit Class

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

        // Convert milliseconds to Seconds
        // using toSeconds() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Seconds = "
                           + time.toSeconds(timeInMilliSec));
    }
}
```

**Output:**

```java
Time 1539585659342 milliSeconds in Seconds = 1539585659

```
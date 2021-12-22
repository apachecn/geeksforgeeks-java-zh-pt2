# Java 中的 TimeUnit toMinutes()方法，示例

> 原文:[https://www . geeksforgeeks . org/time unit-tomi nutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-tominutes-method-in-java-with-examples/)

**时间单位类**的 **toMinutes()** 方法用于从 1970 年 1 月 1 日午夜协调世界时开始，以分钟数的形式获取时间单位对象所表示的时间。

**语法:**

```
public long toMinutes(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。

**返回值:**该方法将**转换后的时长**返回为分钟。

下面的程序说明了 TimeUnit toMinutes()方法的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toMinutes() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = new Date().getTime();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to Minutes
        // using toMinutes() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Minutes = "
                           + time.toMinutes(timeInMilliSec));
    }
}
```

**Output:** 

```
Time 1539585683206 milliSeconds in Minutes = 25659761
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toMinutes() method of TimeUnit Class

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

        // Convert milliseconds to Minutes
        // using toMinutes() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in Minutes = "
                           + time.toMinutes(timeInMilliSec));
    }
}
```

**Output:** 

```
Time 1539585685664 milliSeconds in Minutes = 25659761
```
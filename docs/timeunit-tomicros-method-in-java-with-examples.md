# Java 中的 TimeUnit toMicros()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-tomi cros-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-tomicros-method-in-java-with-examples/)

**时间单位类**的**ToiCross()**方法用于获取从 1970 年 1 月 1 日午夜协调世界时开始，由时间单位对象表示的时间，单位为微秒数。

**语法:**

```java
public long toMicros(long duration)
```

**参数:**该方法接受一个强制参数**持续时间**，即以毫秒为单位的持续时间。

**返回值:**该方法以微秒为单位返回**转换后的持续时间**。

下面的程序举例说明了 TimeUnit toMicros()方法的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toMicros() method of TimeUnit Class

import java.util.concurrent.*;
import java.util.Date;

class GFG {
    public static void main(String args[])
    {
        // Get current time in milliseconds
        long timeInMilliSec = new Date().getTime();

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.MILLISECONDS;

        // Convert milliseconds to MicroSeconds
        // using toMicros() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in MicroSeconds = "
                           + time.toMicros(timeInMilliSec));
    }
}
```

**Output:** 

```java
Time 1539585538596 milliSeconds in MicroSeconds = 1539585538596000
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toMicros() method of TimeUnit Class

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

        // Convert milliseconds to MicroSeconds
        // using toMicros() method
        System.out.println("Time " + timeInMilliSec
                           + " milliSeconds in MicroSeconds = "
                           + time.toMicros(timeInMilliSec));
    }
}
```

**Output:** 

```java
Time 1539585540908 milliSeconds in MicroSeconds = 1539585540908000
```
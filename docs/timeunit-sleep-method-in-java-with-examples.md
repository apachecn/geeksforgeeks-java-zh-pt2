# Java 中的 TimeUnit sleep()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-sleep-in-Java-method-with-examples/](https://www.geeksforgeeks.org/timeunit-sleep-method-in-java-with-examples/)

**时间单位类**的**睡眠()**方法用于使用该时间单位执行线程睡眠。这是一个方便的方法，它将时间参数休眠成 Thread.sleep 方法所需的形式。

**语法:**

```java
public void sleep(long timeout)
           throws InterruptedException
```

**参数:**该方法接受一个强制参数**超时**，这是最小的睡眠时间。如果这小于或等于零，则根本不要睡觉。

**返回值:**这个方法不返回任何东西。

**异常:**此方法抛出**中断异常**如果在睡觉时被中断。

下面的程序说明了 TimeUnit sleep()方法的实现:

**程序 1:**

```java
// Java program to demonstrate
// sleep() method of TimeUnit Class

import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {
        // Get time to sleep
        long timeToSleep = 0L;

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.SECONDS;

        try {

            System.out.println("Going to sleep for "
                               + timeToSleep
                               + " seconds");

            // using sleep() method
            time.sleep(timeToSleep);

            System.out.println("Slept for "
                               + timeToSleep
                               + " seconds");
        }

        catch (InterruptedException e) {
            System.out.println("Interrupted "
                               + "while Sleeping");
        }
    }
}
```

**Output:**

```java
Going to sleep for 0 seconds
Slept for 0 seconds

```

**程序 2:**

```java
// Java program to demonstrate
// sleep() method of TimeUnit Class

import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {
        // Get time to sleep
        long timeToSleep = 10L;

        // Create a TimeUnit object
        TimeUnit time = TimeUnit.SECONDS;

        try {

            System.out.println("Going to sleep for "
                               + timeToSleep
                               + " seconds");

            // using sleep() method
            time.sleep(timeToSleep);

            System.out.println("Slept for "
                               + timeToSleep
                               + " seconds");
        }

        catch (InterruptedException e) {
            System.out.println("Interrupted "
                               + "while Sleeping");
        }
    }
}
```

**Output:**

```java
Going to sleep for 10 seconds
Slept for 10 seconds

```
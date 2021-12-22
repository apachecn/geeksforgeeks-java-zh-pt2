# Java 中的时间单位值()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-values-method-in-java-with-examples/)

**时间单位类**的**值()**方法按照声明的顺序返回一个包含该枚举类型常量的数组。简而言之，该方法用于获取时间单位类的枚举常数。

**语法:**

```java
public static TimeUnit[] values()
```

**返回值:**这个方法返回一个包含这个枚举类型的常量的**数组**，按照它们被声明的顺序

下面程序举例说明了 TimeUnit values()方法:

```java
// Java program to demonstrate
// values() method of TimeUnit Class

import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {

        System.out.println("The Enum constants "
                           + "of TimeUnit Class "
                           + "using TimeUnit.values() "
                           + "are:");

        // Get the array of Enum constants
        // using TimeUnit.values
        // and Iterate over them
        for (TimeUnit constants : TimeUnit.values()) {
            System.out.println(constants);
        }
    }
}
```

**输出:**

```java
The Enum constants of TimeUnit Class using TimeUnit.values() are:
NANOSECONDS
MICROSECONDS
MILLISECONDS
SECONDS
MINUTES
HOURS
DAYS

```
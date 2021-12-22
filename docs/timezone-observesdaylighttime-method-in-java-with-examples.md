# Java 中的 TimeZone observesDaylightTime()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-observesdaylighttime-Java 中的方法-示例/](https://www.geeksforgeeks.org/timezone-observesdaylighttime-method-in-java-with-examples/)

Java 中 **[时区类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的 **observesDaylightTime()** 方法用于检查和验证给定日期是否处于夏令时，或者是否会在未来任何时间发生从标准时间到夏令时的转换。

**语法:**

```java
public boolean observesDaylightTime()
```

**参数:**该方法不取任何参数。

**返回值:**如果传递的日期相对于夏令时无效，则该方法返回布尔值“真”，否则该方法返回布尔值“假”。默认情况下，该方法返回真。

下面的程序说明了 observesDaylightTime()方法在 Java 中的使用:
**示例 1:**

```java
// Java code to demonstrate
// observesDaylightTime() method

import java.util.*;

public class TimeZone_Demo {
    public static void main(String[] args)
    {
        // Creating a time zone object
        TimeZone timeobj
            = TimeZone
                  .getTimeZone("Pacific/Pago_Pago");

        // Displaying the time zone

        System.out.println(timeobj);
        // Verifying daylight
        boolean bool_daylight
            = timeobj.observesDaylightTime();

        // Checking the value of day light
        System.out.println("The result is: "
                           + bool_daylight);
    }
}
```

**Output:**

> sun . util . calendar . zoneinfo[id = " Pacific/Pago _ Pago "，offset=-39600000，dstSavings = 0，
> useDaylight=false，transitions=3，lastRule=null]
> 结果为:false

**例 2:**

```java
// Java code to demonstrate
// inDaylightTime() method

import java.util.*;

public class SimpleTimeZone_Demo {
    public static void main(String[] args)
    {
        // Creating a time zone object
        TimeZone timeobj
            = TimeZone
                  .getTimeZone("Indian/Chagos");

        // Displaying the time zone

        System.out.println(timeobj);
        // Verifying daylight
        boolean bool_daylight
            = timeobj.observesDaylightTime();

        // Checking the value of day light
        System.out.println("The result is: "
                           + bool_daylight);
    }
}
```

**Output:**

> sun . util . calendar . zoneinfo[id = " Indian/Chagos "，offset=21600000，dstSavings = 0，useDaylight=false，transitions=4，lastRule=null]
> 结果为:false

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # observesDaylightTime()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#observesDaylightTime())
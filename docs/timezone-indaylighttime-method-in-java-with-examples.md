# Java 中 TimeZone inDaylightTime()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-indaylighttime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-indaylighttime-method-in-java-with-examples/)

Java 中 **[TimeZone 类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的**inDaylightTime(*Date*)**方法用于检查并验证给定日期是否为夏令时。

**语法:**

```java
public abstract boolean 
    inDaylightTime(Date *date*)
```

**参数:**该方法取日期类型的一个参数*日期*，该日期类型为待验证的给定日期。

**返回值:**如果传递的日期相对于夏令时无效，则该方法返回布尔值“真”，否则该方法返回布尔值“假”。

下面的程序说明了 inDaylightTime()方法在 Java 中的使用:
**示例 1:**

```java
// Java code to demonstrate
// inDaylightTime() method

import java.util.*;

public class SimpleTimeZone_Demo {
    public static void main(String[] args)
    {
        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Europe/Rome");

        // Creating date object
        Date dt = new Date();

        // Verifying daylight
        boolean bool_daylight
            = offtime_zone.inDaylightTime(dt);

        // Checking the value of day light
        System.out.println("Is it in day"
                           + " light saving time? "
                           + bool_daylight);
    }
}
```

**Output:**

```java
Is it in day light saving time? true

```

**例 2:**

```java
// Java code to demonstrate
// inDaylightTime() method

import java.util.*;

public class SimpleTimeZone_Demo {
    public static void main(String[] args)
    {
        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Pacific/Pago_Pago");

        // Creating date object
        Date dt = new Date();

        // Verifying daylight
        boolean bool_daylight
            = offtime_zone.inDaylightTime(dt);

        // Checking the value of day light
        System.out.println("Is it in day"
                           + " light saving time? "
                           + bool_daylight);
    }
}
```

**Output:**

```java
Is it in day light saving time? false

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # inDaylightTime(Java . util . date)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#inDaylightTime(java.util.Date))
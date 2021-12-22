# Java 中的 SimpleTimeZone inDaylightTime()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-indaylighttime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-indaylighttime-method-in-java-with-examples/)

Java 中 **[SimpleTimeZone 类](https://www.geeksforgeeks.org/tag/java-simpletimezone/)** 的 **inDaylightTime( *Date* )方法**用于检查并验证给定日期是否为夏令时。

**语法:**

```java
public boolean inDaylightTime(Date date)
```

**参数:**该方法取**日期**类型的一个参数日期，即待校验的给定日期。

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
        // Creating a time zone object
        SimpleTimeZone simtimeobj
            = new SimpleTimeZone(540, "GMT");

        // Creating date object
        Date dt = new Date();

        // Verifying daylight
        boolean bool_daylight
            = simtimeobj.inDaylightTime(dt);

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

**例 2:**

```java
// Java code to demonstrate
// inDaylightTime() method

import java.util.*;

public class SimpleTimeZone_Demo {
    public static void main(String[] args)
    {
        // Creating a time zone object
        SimpleTimeZone simtimeobj
            = new SimpleTimeZone(400, "AUS");

        // Creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // Set Month
        // MONTH starts with 0 i.e.(0 - Jan)
        c1.set(Calendar.MONTH, 00);

        // Set Date
        c1.set(Calendar.DATE, 30);

        // Set Year
        c1.set(Calendar.YEAR, 2019);

        // Creating a date object
        // with specified time.
        Date dt = c1.getTime();

        // Verifying daylight
        boolean bool_daylight
            = simtimeobj.inDaylightTime(dt);

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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/simple time zone . html # inDaylightTime-Java . util . date-](https://docs.oracle.com/javase/8/docs/api/java/util/SimpleTimeZone.html#inDaylightTime-java.util.Date-)
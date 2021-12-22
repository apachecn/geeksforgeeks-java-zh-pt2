# Java 中的 SimpleTimeZone setStartYear()方法

> 原文:[https://www . geesforgeks . org/simple time zone-setstartyear-method-in-Java/](https://www.geeksforgeeks.org/simpletimezone-setstartyear-method-in-java/)

**简单时区类**的**设置开始年份()**方法用于设置夏令时开始年份。

**语法:**

```java
public void setStartYear(int year)

```

**参数:**该功能接受单个参数**年份**，指定夏令时开始年份。

**返回值:**该方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function SimpleTimeZone.setStartYear()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(500, "US");

        // printing
        System.out.println("SimpleTimeZone: "
                           + obj);

        // setting start year
        obj.setStartYear(2000);

        System.out.println("\nStartYear "
                           + "set to 2000\n");

        // printing the final value
        System.out.println("SimpleTimeZone: "
                           + obj);
    }
}
```

**Output:**

```java
SimpleTimeZone: java.util.SimpleTimeZone[
    id=US,
    offset=500,
    dstSavings=3600000,
    useDaylight=false,
    startYear=0,
    startMode=0,
    startMonth=0,
    startDay=0,
    startDayOfWeek=0,
    startTime=0,
    startTimeMode=0,
    endMode=0,
    endMonth=0,
    endDay=0,
    endDayOfWeek=0,
    endTime=0,
    endTimeMode=0]

StartYear set to 2000

SimpleTimeZone: java.util.SimpleTimeZone[
    id=US,
    offset=500,
    dstSavings=3600000,
    useDaylight=false,
    startYear=2000,
    startMode=0,
    startMonth=0,
    startDay=0,
    startDayOfWeek=0,
    startTime=0,
    startTimeMode=0,
    endMode=0,
    endMonth=0,
    endDay=0,
    endDayOfWeek=0,
    endTime=0,
    endTimeMode=0]

```

**程序 2:**

```java
// program to demonstrate the
// function SimpleTimeZone.setStartYear()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(620, "US");

        // printing
        System.out.println("SimpleTimeZone: "
                           + obj);

        // setting start year
        obj.setStartYear(2018);

        System.out.println("\nStartYear "
                           + "set to 2018\n");

        // printing the final value
        System.out.println("SimpleTimeZone: "
                           + obj);
    }
}
```

**Output:**

```java
SimpleTimeZone: java.util.SimpleTimeZone[
    id=US,
    offset=620,
    dstSavings=3600000,
    useDaylight=false,
    startYear=0,
    startMode=0,
    startMonth=0,
    startDay=0,
    startDayOfWeek=0,
    startTime=0,
    startTimeMode=0,
    endMode=0,
    endMonth=0,
    endDay=0,
    endDayOfWeek=0,
    endTime=0,
    endTimeMode=0]

StartYear set to 2018

SimpleTimeZone: java.util.SimpleTimeZone[
    id=US,
    offset=620,
    dstSavings=3600000,
    useDaylight=false,
    startYear=2018,
    startMode=0,
    startMonth=0,
    startDay=0,
    startDayOfWeek=0,
    startTime=0,
    startTimeMode=0,
    endMode=0,
    endMonth=0,
    endDay=0,
    endDayOfWeek=0,
    endTime=0,
    endTimeMode=0]

```
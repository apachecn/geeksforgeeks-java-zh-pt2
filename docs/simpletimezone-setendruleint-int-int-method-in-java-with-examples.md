# Java 中 SimpleTimeZone setEndRule(int，int，int)方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-setendruleint-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-setendruleint-int-int-method-in-java-with-examples/)

Java 中 SimpleTimeZone 类的 setEndRule(int*end fmonth*、int*end fday*、int*end ftime*)方法用于将某一天光节约时间的特定规则设置为给定月份内的固定日期。

**语法:**

```
public void setEndRule(int *endofMonth*, 
                            int *endofDay*, 
                            int *endofTime*)
```

**参数:**该方法取三个参数:

*   *月末*:整数类型，指夏令时的月末。
*   *endofDay* :整数类型，指夏令时的结束日。
*   *endofTime* :整数类型，指夏令时的结束时间。

**返回值:**该方法不返回值。

下面的程序说明了 setEndRule()方法在 Java 中的使用:
**示例 1:**

```
// Java code to demonstrate
// setEndRule() method

import java.util.*;

public class SimpleTimeZone_Demo {
    public static void main(String[] args)
    {

        // Creating SimpleTimeZone object
        SimpleTimeZone simtimeobj
            = new SimpleTimeZone(100, "GMT");

        // Displaying the Initial value
        System.out.println(
            "Initial value: " + simtimeobj);

        // Setting an EnDRule
        simtimeobj.setEndRule(Calendar.APRIL,
                              28, 3600000);

        // Displaying the New value
        System.out.println(
            "New value: " + simtimeobj);
    }
}
```

**Output:**

```
Initial value: java.util.SimpleTimeZone[id=GMT, offset=100, dstSavings=3600000,
useDaylight=false, startYear=0, startMode=0, startMonth=0, startDay=0, startDayOfWeek=0,
startTime=0, startTimeMode=0, endMode=0, endMonth=0, endDay=0, endDayOfWeek=0, endTime=0,
endTimeMode=0]

New value: java.util.SimpleTimeZone[id=GMT, offset=100, dstSavings=3600000,
useDaylight=false, startYear=0, startMode=0, startMonth=0, startDay=0, startDayOfWeek=0,
startTime=0, startTimeMode=0, endMode=1, endMonth=3, endDay=28, endDayOfWeek=0,
endTime=3600000, endTimeMode=0]

```

**例 2:**

```
// Java code to demonstrate
// setEndRule() method

import java.util.*;

public class SimpleTimeZone_Demo {
    public static void main(String[] args)
    {

        // Creating SimpleTimeZone object
        SimpleTimeZone simtimeobj
            = new SimpleTimeZone(120, "GMT");

        // Displaying the Initial value
        System.out.println(
            "Initial value: " + simtimeobj);

        // Setting an EnDRule
        simtimeobj.setEndRule(Calendar.JANUARY,
                              15, 3600000);

        // Displaying the New value
        System.out.println(
            "New value: " + simtimeobj);
    }
}
```

**Output:**

```
Initial value: java.util.SimpleTimeZone[id=GMT, offset=120, dstSavings=3600000,
useDaylight=false, startYear=0, startMode=0, startMonth=0, startDay=0, startDayOfWeek=0,
startTime=0, startTimeMode=0, endMode=0, endMonth=0, endDay=0, endDayOfWeek=0,
endTime=0, endTimeMode=0]

New value: java.util.SimpleTimeZone[id=GMT, offset=120, dstSavings=3600000,
useDaylight=false, startYear=0, startMode=0, startMonth=0, startDay=0, startDayOfWeek=0,
startTime=0, startTimeMode=0, endMode=1, endMonth=0, endDay=15, endDayOfWeek=0,
endTime=3600000, endTimeMode=0]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/simple time zone . html # setEndRule(int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/util/SimpleTimeZone.html#setEndRule(int,int,int))
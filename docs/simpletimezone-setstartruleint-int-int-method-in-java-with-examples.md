# Java 中 SimpleTimeZone setStartRule(int，int，int)方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-setstartruleint-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-setstartruleint-int-int-method-in-java-with-examples/)

Java 中 **[SimpleTimeZone 类的**setStartRule(int*startof month*、int *startofDay* 、int *startofTime* )方法**用于在给定的月份内将某个特定的日光节约时间的开始规则设置为一个固定的日期。](https://www.geeksforgeeks.org/tag/java-simpletimezone/)**

**语法:**

```
public void setStartRule(int *startofMonth*, 
                              int *startofDay*, 
                              int *startofTime*)
```

**参数:**该方法取三个参数:

*   *起始月*:整数类型，指夏令时的起始月。
*   *开始日期*:整数类型，指夏令时的开始日期。
*   *开始时间*:整数类型，指夏令时的开始时间。

**返回值:**该方法不返回值。

以下程序说明了 setStartRule()方法在 Java 中的使用:
**示例 1:**

```
// Java code to demonstrate
// setStartRule() method

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

        // Setting an StartRule
        simtimeobj.setStartRule(Calendar.APRIL,
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
useDaylight=false, startYear=0, startMode=1, startMonth=3, startDay=28, startDayOfWeek=0,
startTime=3600000, startTimeMode=0, endMode=0, endMonth=0, endDay=0, endDayOfWeek=0,
endTime=0, endTimeMode=0]

```

**例 2:**

```
// Java code to demonstrate
// setStartRule() method

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

        // Setting an StartRule
        simtimeobj.setStartRule(Calendar.JANUARY,
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
startTime=0, startTimeMode=0, endMode=0, endMonth=0, endDay=0, endDayOfWeek=0, endTime=0,
endTimeMode=0]

New value: java.util.SimpleTimeZone[id=GMT, offset=120, dstSavings=3600000,
useDaylight=false, startYear=0, startMode=1, startMonth=0, startDay=15, startDayOfWeek=0,
startTime=3600000, startTimeMode=0, endMode=0, endMonth=0, endDay=0, endDayOfWeek=0,
endTime=0, endTimeMode=0]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/simple time zone . html # setStartRule(int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/util/SimpleTimeZone.html#setStartRule(int,int,int))
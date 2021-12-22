# Java 中的时区克隆()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-clone-in-Java-method-with-examples/](https://www.geeksforgeeks.org/timezone-clone-method-in-java-with-examples/)

Java 中**时区类**的**克隆()**方法用于创建现有时区的相同副本。

**语法:**

```java
time_zone.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回**一个时区实例**，它是该时区的副本。

下面的程序说明了时区克隆()方法的工作原理:

**例 1:**

```java
// Java code to illustrate clone() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating an object of TimeZone class.
        TimeZone time_zone
            = TimeZone.getDefault();
        System.out.println("Original TimeZone: "
                           + time_zone);

        System.out.println();

        // Cloning and displaying the time zone
        System.out.println("Cloned TimeZone: "
                           + time_zone.clone());
    }
}
```

**Output:**

> 原始时区:
> sun . util . calendar . zoneinfo[id = " Etc/UTC "，偏移量=0，dstSavings = 0，useDaylight=false，transitions=0，lastRule=null]
> 
> 克隆时区:
> sun . util . calendar . zoneinfo[id = " Etc/UTC "，偏移量=0，dstSavings = 0，useDaylight=false，transitions=0，lastRule=null]

**例 2:**

```java
// Java code to illustrate clone() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // creating Timezone object whose id is Europe/Berlin
        TimeZone time_zone
            = TimeZone.getTimeZone("Europe/Berlin");

        System.out.println("Original TimeZone: "
                           + time_zone);

        System.out.println();

        // Cloning and displaying the time zone
        System.out.println("Cloned TimeZone: "
                           + time_zone.clone());
    }
}
```

**Output:**

> 原始时区:
> sun . util . calendar . zoneinfo[id = " Europe/Berlin "，offset=3600000，dstSavings=3600000，useDaylight=true，transitions=143，last rule = Java . util . simple time zone[id = Europe/Berlin，offset=3600000，dstSavings=3600000，useDaylight=true，startYear=0，startMode=2，startMonth=2，startDay=-1，startDayOfWeek
> 
> 克隆时区:
> sun . util . calendar . zoneinfo[id = " Europe/Berlin "，offset=3600000，dstSavings=3600000，useDaylight=true，transitions=143，last rule = Java . util . simple time zone[id = Europe/Berlin，offset=3600000，dstSavings=3600000，useDaylight=true，startYear=0，startMode=2，startMonth=2，startDay=-1，startDayOfWeek
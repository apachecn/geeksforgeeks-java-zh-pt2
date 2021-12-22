# 时区设置默认()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/time zone-set default-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-setdefault-method-in-java-with-examples/)

Java 中 **[TimeZone 类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的**setDefault(TimeZone*zone*)**方法用于设置 time zone 类的 **[getDefault()](https://www.geeksforgeeks.org/timezone-getdefault-method-in-java-with-examples/)** 方法返回的对象的时区。

**语法:**

```
public static void 
    setDefault(TimeZone *zone*)
```

**参数:**该方法取时区类型的一个参数*区域*，指的是新的默认时区。

**返回值:**该方法不返回值。

下面的程序说明了时区的 setDefault()方法的工作原理。
**例 1:**

```
// Java code to illustrate setDefault() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {
        // Creating an object of TimeZone class.
        TimeZone time_zone_default
            = TimeZone.getTimeZone("Europe/Rome");

        time_zone_default.setDefault(time_zone_default);

        // Displaying the default TimeZone
        System.out.println("Default TimeZone: "
                           + time_zone_default);
    }
}
```

**Output:**

> 默认时区:sun . util . calendar . zoneinfo[id = " Europe/Rome "，offset=3600000，
> dstSavings=3600000，useDaylight=true，transitions=169，last rule = Java . util . simple time zone
> [id = Europe/Rome，offset=3600000，dstSavings=3600000，useDaylight=true，startYear=0，
> startMode=2，startMonth=2，startDay=-1

**例 2:**

```
// Java code to illustrate setDefault() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {
        // Creating an object of TimeZone class.
        TimeZone time_zone_default
            = TimeZone.getTimeZone("Pacific/Pago_Pago");

        time_zone_default.setDefault(time_zone_default);

        // Displaying the default TimeZone
        System.out.println("Default TimeZone: "
                           + time_zone_default);
    }
}
```

**Output:**

> 默认时区:sun . util . calendar . zoneinfo[id = " Pacific/Pago _ Pago "，
> offset=-39600000，dstSavings = 0，useDaylight=false，transitions=3，lastRule=null]

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/util/time zone . html # setdefault(Java . util . time zone)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#setDefault(java.util.TimeZone))
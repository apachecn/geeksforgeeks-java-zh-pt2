# Java 中的时区获取保存()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-getdstssavings-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getdstsavings-method-in-java-with-examples/)

Java 中 **TimeZone 类**的**getdstssaving()**方法是用来知道需要加到本地标准时间的时间量来得到挂钟时间。

**语法:**

```java
public int getDSTSavings()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以毫秒为单位返回**需要加入当地标准时间的时间量**得到挂钟时间。这就是所谓的**储蓄时间**。

下面的程序说明了时区的 getDSTSavings()方法的工作:
**示例 1:**

```java
// Java code to illustrate getDSTSavings() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone
                  .getTimeZone("Pacific/Pago_Pago");

        // Knowing the DST
        System.out.println("The DST is: "
                           + offtime_zone.getDSTSavings());
    }
}
```

**Output:**

```java
The DST is: 0

```

**例 2:**

```java
// Java code to illustrate getDSTSavings() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Europe/Rome");

        // Knowing the DST
        System.out.println("The DST is: "
                           + offtime_zone.getDSTSavings());
    }
}
```

**Output:**

```java
The DST is: 3600000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getdstssavings()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDSTSavings())
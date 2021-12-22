# Java 中的时区 getRawOffset()方法，示例

> 原文:[https://www . geeksforgeeks . org/time zone-getraw offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getrawoffset-method-in-java-with-examples/)

Java 中**时区类**的**getrawpoffset()**方法用于知道需要添加到 UTC 中的时间量(以毫秒为单位)，以获得该时区的标准时间。

**语法:**

```java
public abstract int getRawOffset()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以毫秒为单位返回**需要添加到世界协调时的时间量**，以获得该时区的标准时间。

以下程序说明了时区的 getRawOffset()方法的工作:
**示例 1:**

```java
// Java code to illustrate getRawOffset() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Pacific/Pago_Pago");

        // Knowing the rawOffset time
        System.out.println("The rawOffset time is: "
                           + offtime_zone.getRawOffset());
    }
}
```

**Output:**

```java
The rawOffset time is: -39600000

```

**例 2:**

```java
// Java code to illustrate getRawOffset() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Europe/Rome");

        // Knowing the rawOffset time
        System.out.println("The rawOffset time is: "
                           + offtime_zone.getRawOffset());
    }
}
```

**Output:**

```java
The rawOffset time is: 3600000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getRawOffset()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDSTSavings())
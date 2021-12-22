# 时区 getDisplayName()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/time zone-getdisplayname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getdisplayname-method-in-java-with-examples/)

Java 中 **TimeZone 类**的 **getDisplayName()** 方法用来获取这个 TimeZone 的一个用户容易理解的特定名称。该名称适用于演示和显示目的。

**语法:**

```
public final String getDisplayName()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回时区的**显示名称。**

下面的程序说明了时区的 getDisplayName()方法的工作:

```
// Java code to illustrate getDisplayName() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {
        // Creating an object of TimeZone class.
        TimeZone time_zone
            = TimeZone.getDefault();

        // Displaying the display name of TimeZone
        System.out.println("The TimeZone: "
                           + time_zone.getDisplayName());
    }
}
```

**输出:**

```
The TimeZone: Coordinated Universal Time

```
# Java 中的 TimeZone getID()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-getid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getid-method-in-java-with-examples/)

Java 中 **TimeZone 类**的 **getID()** 方法用于获取特定时区的官方 ID。

**语法:**

```java
public String getID()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回时区的**标识。**

下面的程序说明了时区的 getID()方法的工作:
**例 1:**

```java
// Java code to illustrate getID() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone 
= TimeZone.getTimeZone("Pacific/Pago_Pago");

        // Knowing the DST
        System.out.println("The ID is: " 
+ offtime_zone.getID());
    }
}
```

**Output:**

```java
The ID is: Pacific/Pago_Pago

```

**实施例 2:**

```java
// Java code to illustrate getID() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone 
= TimeZone.getTimeZone("Europe/Rome");

        // Knowing the DST
        System.out.println("The ID is: "
 + offtime_zone.getID());
    }
}
```

**Output:**

```java
The ID is: Europe/Rome

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getID()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getID())
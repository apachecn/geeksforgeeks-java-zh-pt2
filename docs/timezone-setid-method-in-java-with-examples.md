# Java 中的 TimeZone setID()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-setid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-setid-method-in-java-with-examples/)

Java 中 **[时区类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的**设置标识(字符串*标识* )** 方法用于设置该时区的时区标识。在此操作期间，不会更改时区对象的其他数据。

**语法:**

```
public void setID(String *ID*)
```

**参数:**该方法采用字符串类型的一个参数*标识*，该标识是指时区的新标识。

**返回值:**该方法不返回值。

下面的程序说明了时区类的 setID()方法的使用:
**示例 1:**

```
// Java code to illustrate setID() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone(
                "Pacific/Pago_Pago");

        // set time zone ID
        offtime_zone.setID("GMT+05:00");

        // Knowing the DST
        System.out.println("The ID is: "
                           + offtime_zone.getID());
    }
}
```

**Output:**

```
The ID is: GMT+05:00

```

**例 2:**

```
// Java code to illustrate setID() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getDefault();

        // set time zone ID
        offtime_zone.setID("GMT+05:30");

        // Knowing the DST
        System.out.println("The ID is: "
                           + offtime_zone.getID());
    }
}
```

**Output:**

```
The ID is: GMT+05:30

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # setID(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#setID(java.lang.String))
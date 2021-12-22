# Java 中的 TimeZone setRawOffset()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-setrawpoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-setrawoffset-method-in-java-with-examples/)

Java 中 **[时区类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的**set raw offset(int*offset millis*)**方法用于将基准时区偏移量设置为 GMT。该偏移值可以是世界协调时，以获得当地时间。

**语法:**

```
public abstract void 
    setRawOffset(int *offsetMillis*)
```

**参数:**该方法接受整数类型的单个参数*偏移量*，该参数指定给定的基准时区相对于格林尼治标准时间的偏移量。

**返回值:**该方法不返回值。

下面的程序说明了上述功能:
**程序 1:**

```
// Program to demonstrate the
// setRawOffset()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create time zone object
        TimeZone obj
            = TimeZone.getTimeZone("Pacific/Pago_Pago");

        // Printing RawOffset value
        System.out.println("Initially RawOffset is = "
                           + obj.getRawOffset());

        // Setting RawOffset on object obj
        obj.setRawOffset(6000000);
        System.out.println("RawOffset "
                           + "set to 6000000");

        // Printing RawOffset value
        System.out.println("Current RawOffset is = "
                           + obj.getRawOffset());
    }
}
```

**Output:**

```
Initially RawOffset is = -39600000
RawOffset set to 6000000
Current RawOffset is = 6000000

```

**程序 2:**

```
// Program to demonstrate the
// setRawOffset()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create time zone object
        TimeZone obj
            = TimeZone.getTimeZone("Europe/Rome");

        // Printing RawOffset value
        System.out.println("Inittally RawOffset is = "
                           + obj.getRawOffset());

        // Setting RawOffset on object obj
        obj.setRawOffset(8000000);
        System.out.println("RawOffset "
                           + "set to 8000000");

        // Printing RawOffset value
        System.out.println("Current RawOffset is = "
                           + obj.getRawOffset());
    }
}
```

**Output:**

```
Inittally RawOffset is = 3600000
RawOffset set to 8000000
Current RawOffset is = 8000000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # setRawOffset(int)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#setRawOffset(int))
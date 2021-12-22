# 时区使用 Java 中的 aylightTime()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-usedaylighttime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-usedaylighttime-method-in-java-with-examples/)

**[时区类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的 **useDaylightTime()** 方法用于查询该时区是否使用夏令时。

**语法:**

```
public abstract boolean useDaylightTime()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回两个布尔值之一:

*   如果该时区使用夏令时，则为“true”
*   如果该时区不使用夏令时，则为“false”

下面的程序演示了上述功能:
**例 1:**

```
// Program to demonstrate the
// useDaylightTime()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create TimeZone object
        TimeZone obj
            = TimeZone.getTimeZone("Europe/Rome");

        // Checking day light time
        // and displaying the result
        System.out.println("Day light time is = "
                           + obj.useDaylightTime());
    }
}
```

**Output:**

```
Day light time is = true

```

**例 2:**

```
// Program to demonstrate the
// useDaylightTime()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create TimeZone object
        TimeZone obj
            = TimeZone.getTimeZone("Pacific/Pago_Pago");

        // checking day light time
        // and printing the result
        System.out.println("Day light time is = "
                           + obj.useDaylightTime());
    }
}
```

**Output:**

```
Day light time is = false

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # useDaylightTime()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#useDaylightTime())
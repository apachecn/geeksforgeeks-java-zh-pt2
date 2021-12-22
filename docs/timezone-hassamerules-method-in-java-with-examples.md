# 时区在 Java 中有一个简单的()方法，带有示例

> 原文:[https://www . geesforgeks . org/time zone-hassamures-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-hassamerules-method-in-java-with-examples/)

Java 中**时区类**的 **hasSameRules()** 方法用于检查两个时区之间的相等性。如果指定的时区与其他时区具有相同的规则和偏移值，则该方法返回 True。

**语法:**

```
public boolean hasSameRules(TimeZone TimeZone_2)
```

**参数:**该方法取对象类型的一个参数 **TimeZone_2** ，该参数是指需要与该时区进行比较的时区。

**返回值:**如果两个时区共享相同的规则和偏移值，并且只有一个例外，则该方法返回**布尔值“真”**“假”。

下面的程序说明了 hasSameRules()方法的工作时区:

```
// Java code to illustrate hasSameRules() method

import java.util.*;

public class TimeZone_Demo {
    public static void main(String args[])
    {

        // Creating the first TimeZone
        TimeZone first_time_zone
            = TimeZone.getDefault();

        // Creating the second TimeZone
        TimeZone sec_time_zone
            = TimeZone.getDefault();

        // Applying hasSameRules() to check for equality
        System.out.println("The equality holds: "
                           + first_time_zone
                                 .hasSameRules(sec_time_zone));
    }
}
```

**输出:**

```
The equality holds: true

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # hassamures()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDSTSavings())
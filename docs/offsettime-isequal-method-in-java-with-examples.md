# Java 中的 OffsetTime isEqual()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-isequal-method-in-java-with-examples/)

Java 格式的 OffsetTime 类的 **isEqual()** 方法检查传递的时间是否等于参数中指定的时间。

**语法:**

```
public boolean isEqual(OffsetTime other)

```

**参数:**此方法接受单个强制参数**其他**，指定要比较的时间。

**返回值:**如果日期等于通过日期则返回真，否则返回假。

以下程序说明了 *isEqual()* 方法:

**程序 1 :**

```
// Java program to demonstrate the isEqual() method
import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time1
            = OffsetTime.parse("15:30:30+07:00");

        // Parses the time
        OffsetTime time2
            = OffsetTime.parse("15:20:30+07:00");

        // gets the time1
        System.out.println("time1: " + time1);

        // gets the time2
        System.out.println("time1: " + time2);

        System.out.println("time1 is equal to time2: "
                           + time1.isEqual(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:20:30+07:00
time1 is equal to time2: false

```

**程序二** :

```
// Java program to demonstrate the isEqual() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time1
            = OffsetTime.parse("15:30:30+07:00");

        // Parses the time
        OffsetTime time2
            = OffsetTime.parse("15:30:30+07:00");

        // gets the time1
        System.out.println("time1: "
                           + time1);

        // gets the time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 is equals to time2: "
                           + time1.isEqual(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:30:30+07:00
time1 is equals to time2: true

```

**参考**:[https://www . tutorialspoint . com/javatime/javatime _ offsettime _ isequal . htm](https://www.tutorialspoint.com/javatime/javatime_offsettime_isequal.htm)
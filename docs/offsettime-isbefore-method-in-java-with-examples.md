# Java 中的 OffsetTime isBefore()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-isbefore-method-in-java-with-examples/)

Java 格式的 OffsetTime 类的 **isBefore()** 方法检查传递的时间是否在参数中指定的时间之前。

**语法:**

```
public boolean isBefore(OffsetTime other)

```

**参数:**此方法接受单个强制参数**其他**，指定要比较的时间。

**返回值:**如果日期在过去的日期之前，则返回真，否则返回假。

以下程序说明了 *isBefore()* 方法:

**程序 1 :**

```
// Java program to demonstrate the isBefore() method
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
        System.out.println("time1: "
                           + time1);

        // gets the time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 is before time2: "
                           + time1.isBefore(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:20:30+07:00
time1 is before time2: false

```

**程序二** :

```
// Java program to demonstrate the isBefore() method

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

        System.out.println("time1 is before time2: "
                           + time1.isBefore(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:30:30+07:00
time1 is before time2: false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettimee . html # is before-Java . time . offsettimee-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#isBefore-java.time.OffsetTime-)
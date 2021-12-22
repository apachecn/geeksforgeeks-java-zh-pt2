# 带示例的 Java 中的 offsettimecomparteto()方法

> 原文:[https://www . geeksforgeeks . org/offsettime-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-compareto-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **compareTo()** 方法将这个时间与另一个时间进行比较，如果它们相等，则返回零，或者根据比较结果返回正整数或负整数。

**语法:**

```
public int compareTo(OffsetTime other)

```

**参数:**该方法接受单个强制参数**其他**，指定要比较的其他时间。

**返回值:**返回比较器值。如果另一个日期小于，它将返回一个负的*值；如果大于，它将返回一个正的*值。

**异常**:如果传递的另一个日期为空，函数抛出*空指针异常*。

下面的程序说明了*比较()*的方法:

**程序 1 :**

```
// Java program to demonstrate the compareTo() method

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

        // gets the offset time1
        System.out.println("time1: "
                           + time1);

        // gets the offset time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 when compared"
                           + " to time2 returns: "
                           + time1.compareTo(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:30:30+07:00
time1 when compared to time2 returns: 0

```

**程序二** :

```
// Java program to demonstrate the compareTo() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time1
            = OffsetTime.parse("15:30:30+07:00");

        // Parses the time
        OffsetTime time2
            = OffsetTime.parse("12:10:30+07:00");

        // gets the offset time1
        System.out.println("time1: "
                           + time1);

        // gets the offset time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 when compared"
                           + " to time2 returns: "
                           + time1.compareTo(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 12:10:30+07:00
time1 when compared to time2 returns: 1

```

**程序 3:** :

```
// Java program to demonstrate the compareTo() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time1
            = OffsetTime.parse("15:30:30+07:00");

        // Parses the time
        OffsetTime time2
            = OffsetTime.parse("17:10:30+07:00");

        // gets the offset time1
        System.out.println("time1: "
                           + time1);

        // gets the offset time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 when compared"
                           + " to time2 returns: "
                           + time1.compareTo(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 17:10:30+07:00
time1 when compared to time2 returns: -1

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettine . html # compare to-Java . time . offsettine-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#compareTo-java.time.OffsetTime-)
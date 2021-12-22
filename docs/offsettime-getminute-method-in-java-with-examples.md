# Java 中的 OffsetTime getMinute()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-getminute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-getminute-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **getMinute()** 方法用于从这个 OffsetTime 实例中获取分钟字段的值。

**语法:**

```
public int getMinute()

```

**参数:**该方法接受不接受任何参数。

**返回值:**返回 0 到 59 范围内的分钟。

下面的程序说明了 *getMinute()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getMinute() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("15:10:30+07:00");

        // gets the minute in time
        System.out.println("minute: " + time.getMinute());
    }
}
```

**输出:**

```
minute: 10

```

**程序二** :

```
// Java program to demonstrate the getHour() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("11:30:30+06:00");

        // gets minute in the time
        System.out.println("Minute: " + time.getMinute());
    }
}
```

**输出:**

```
Minute: 30

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # getMinute–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#getMinute--)
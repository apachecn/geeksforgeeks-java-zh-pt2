# Java 中的 OffsetTime getHour()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-get hour-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-gethour-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **getHour()** 方法用于从这个 OffsetTime 实例中获取一天中的小时字段的值。

**语法:**

```
public int getHour()

```

**参数:**该方法不接受任何参数。

**返回值:**返回 0 到 23 之间的小时数。

以下程序说明了 *getHour()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getHour() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("15:30:30+07:00");

        // gets the time
        System.out.println("Hour: " + time.getHour());
    }
}
```

**输出:**

```
Hour: 15

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

        // gets the time
        System.out.println("Hour: " + time.getHour());
    }
}
```

**输出:**

```
Hour: 11

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # getHour–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#getHour--)
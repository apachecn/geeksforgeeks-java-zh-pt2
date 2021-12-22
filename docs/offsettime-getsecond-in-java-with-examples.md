# Java 中的 OffsetTime getSecond()示例

> 原文:[https://www . geeksforgeeks . org/offsettime-getsecond-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-getsecond-in-java-with-examples/)

Java 中 offsetTime 类的 **getSecond()** 方法用于从这个 OffsetTime 实例中获取分钟秒字段的值。

**语法:**

```
public int getSecond()

```

**参数:**该方法接受不接受任何参数。

**返回值:**返回 0 到 59 的分钟秒数。

以下程序说明了 *getSecond()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getSecond() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("15:10:30+07:00");

        // gets the second in time
        System.out.println("second: " + time.getSecond());
    }
}
```

**输出:**

```
second: 30

```

**输出:**

```
second: 30

```

**程序二** :

```
// Java program to demonstrate the getSecond() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("11:30:50+06:00");

        // gets the second in time
        System.out.println("second: " + time.getSecond());
    }
}
```

**输出:**

```
second: 50

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # getSecond–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#getSecond--)
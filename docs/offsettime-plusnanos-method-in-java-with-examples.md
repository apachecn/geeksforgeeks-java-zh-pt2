# Java 中的 OffsetTime plusNanos()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-plusnanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-plusnanos-method-in-java-with-examples/)

**偏置时间类**的 **plusNanos()** 方法用于向该偏置时间添加指定数量的纳秒值，并将结果作为偏置时间对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```
public OffsetTime plusNanos(long nanosecondsToAdd)

```

**参数:**该方法接受单个参数**nanossecond 添加**，即需要添加的纳秒值，可以是负值。

**返回值:**这个方法根据这个时间加上纳秒返回一个**偏置时间**。

下面的程序说明了 plusNanos()方法:

**程序 1:**

```
// Java program to demonstrate
// OffsetTime.plusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("12:25:10+01:00");

        // print OffsetTime
        System.out.println("OffsetTime before add: "
                           + time);

        // add 34000000 nanoseconds using plusNanos()
        OffsetTime value = time.plusNanos(34000000);

        // print result
        System.out.println("OffsetTime after add: "
                           + value);
    }
}
```

**输出:**

```
OffsetTime before add: 12:25:10+01:00
OffsetTime after add: 12:25:10.034+01:00

```

**程序二:**

```
// Java program to demonstrate
// OffsetTime.plusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("12:25:10+01:00");

        // print OffsetTime
        System.out.println("OffsetTime before add: "
                           + time);

        // add -971200000 nanoseconds  using plusNanos()
        OffsetTime value = time.plusNanos(-971200000);

        // print result
        System.out.println("OffsetTime after add: "
                           + value);
    }
}
```

**输出:**

```
OffsetTime before add: 12:25:10+01:00
OffsetTime after add: 12:25:09.028800+01:00

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # plusNanos-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#plusNanos-long-)
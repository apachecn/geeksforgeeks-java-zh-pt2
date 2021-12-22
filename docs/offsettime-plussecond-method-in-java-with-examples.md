# Java 中的 OffsetTime plusSecond()方法，示例

> 原文:[https://www . geeksforgeeks . org/offsettime-plussecond-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-plussecond-method-in-java-with-examples/)

**偏移时间类**的 **plusSeconds()** 方法用于将指定的秒数值添加到该偏移时间，并将结果作为偏移时间对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public OffsetTime plusSeconds(long SecondsToAdd)

```

**参数:**此方法接受单个参数**秒添加**，即要添加的秒值，可以是负值。

**返回值:**该方法根据该时间返回一个**偏置时间**，并加上秒数。

下面的程序说明了 plusSeconds()方法:

**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.plusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("21:15:10+11:10");

        // print OffsetTime
        System.out.println("OffsetTime before addition: "
                           + time);

        // add 200 Seconds using plusSeconds()
        OffsetTime value = time.plusSeconds(200);

        // print result
        System.out.println("OffsetTime after addition: "
                           + value);
    }
}
```

**输出:**

```java
OffsetTime before addition: 21:15:10+11:10
OffsetTime after addition: 21:18:30+11:10

```

**程序二:**

```java
// Java program to demonstrate
// OffsetTime.plusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("14:25:10+01:10");

        // print OffsetTime
        System.out.println("OffsetTime before addition: "
                           + time);

        // add -3400 Seconds using plusSeconds()
        OffsetTime value = time.plusSeconds(-3400);

        // print result
        System.out.println("OffsetTime after addition: "
                           + value);
    }
}
```

**输出:**

```java
OffsetTime before addition: 14:25:10+01:10
OffsetTime after addition: 13:28:30+01:10

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # plus seconds-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#plusSeconds-long-)
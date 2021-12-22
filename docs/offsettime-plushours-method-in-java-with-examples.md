# Java 中的 OffsetTime plusHours()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-plushours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-plushours-method-in-java-with-examples/)

**偏移时间类**的 **plusHours()** 方法用于将指定的小时数值添加到该偏移时间，并将结果作为偏移时间对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public OffsetTime plusHours(long hoursToAdd)

```

**参数:**此方法接受单个参数**小时添加**，即要添加的小时值，可以是负值。

**返回值:**该方法根据该时间返回一个**偏置时间**，并加上小时。

下面的程序说明了 plusHours()方法:

**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.plusHours() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("12:16:10+11:00");

        // print OffsetTime
        System.out.println("OffsetTime before addition : "
                           + time);

        // added 3 hours using plusHours()
        OffsetTime value = time.plusHours(3);

        // print result
        System.out.println("OffsetTime after addition : "
                           + value);
    }
}
```

**输出:**

```java
OffsetTime before addition : 12:16:10+11:00
OffsetTime after addition : 15:16:10+11:00

```

**程序二:**

```java
// Java program to demonstrate
// OffsetTime.plusHours() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("13:20:15+13:00");

        // print OffsetTime
        System.out.println("OffsetTime before addition : "
                           + time);

        // added -10 hours using plusHours()
        OffsetTime value = time.plusHours(-10);

        // print result
        System.out.println("OffsetTime after addition : "
                           + value);
    }
}
```

**输出:**

```java
OffsetTime before addition : 13:20:15+13:00
OffsetTime after addition : 03:20:15+13:00

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # plusHours-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#plusHours-long-)
# Java 中的 OffsetTime plusMinutes()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-plusminutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-plusminutes-method-in-java-with-examples/)

**偏移时间类**的 **plusMinutes()** 方法用于将指定的分钟数值添加到该偏移时间，并将结果作为偏移时间对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```
public OffsetTime plusMinutes(long MinutesToAdd)

```

**参数:**此方法接受单个参数**分钟添加**，即要添加的分钟值，可以是负值。

**返回值:**该方法返回一个基于该时间的**偏置时间**，并添加分钟数。

下面的程序说明了 plusMinutes()方法:

**程序 1:**

```
// Java program to demonstrate
// OffsetTime.plusMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("14:25:10+11:00");

        // print OffsetTime
        System.out.println("OffsetTime before addition: "
                           + time);

        // add 55 Minutes using plusMinutes()
        OffsetTime value = time.plusMinutes(55);

        // print result
        System.out.println("OffsetTime after addition: "
                           + value);
    }
}
```

**输出:**

```
OffsetTime before addition: 14:25:10+11:00
OffsetTime after addition: 15:20:10+11:00

```

**程序二:**

```
// Java program to demonstrate
// OffsetTime.plusMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetTime object
        OffsetTime time
            = OffsetTime.parse("14:25:10+11:00");

        // print OffsetTime
        System.out.println("OffsetTime before addition: "
                           + time);

        // add -600 Minutes using plusMinutes()
        OffsetTime value = time.plusMinutes(-600);

        // print result
        System.out.println("OffsetTime after addition: "
                           + value);
    }
}
```

**输出:**

```
OffsetTime before addition: 14:25:10+11:00
OffsetTime after addition: 04:25:10+11:00

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # plusMinutes-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#plusMinutes-long-)
# Java 中的 OffsetTime getOffset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-getoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-getoffset-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **getOffset()** 方法从解析的时间中获取区域偏移量，比如'+05:00 '，可以作为一个例子。

**语法:**

```
public ZoneOffset getOffset()

```

**参数:**该方法不接受任何参数。

**返回值:**返回区域偏移量，不为空。

以下程序说明了 *getOffset()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getOffset() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time
            = OffsetTime.parse("15:30:30+07:00");

        // gets the offset time
        System.out.println("Offset time: "
                           + time.getOffset());
    }
}
```

**输出:**

```
Offset time: +07:00

```

**程序二** :

```
// Java program to demonstrate the getOffset() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time
            = OffsetTime.parse("11:20:10+04:00");

        // gets the offset time
        System.out.println("Offset time: "
                           + time.getOffset());
    }
}
```

**输出:**

```
Offset time: +04:00

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # getOffset–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#getOffset--)
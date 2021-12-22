# Java 中的 offsettimeisaafter()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-is after-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-isafter-method-in-java-with-examples/)

Java 格式的 OffsetTime 类的**isaafter()**方法检查传递的时间是否在参数中指定的时间之后。

**语法:**

```
public boolean isAfter(OffsetTime other)

```

**参数:**此方法接受单个强制参数**其他**，指定要比较的时间。

**返回值:**如果日期在过去的日期之后，则返回真，否则返回假。

以下程序说明了 *isAfter()* 方法:

**程序 1 :**

```
// Java program to demonstrate the isAfter() method
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

        // prints the time1
        System.out.println("time1: "
                           + time1);

        // prints the time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 is after time2: "
                           + time1.isAfter(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:20:30+07:00
time1 is after time2: true

```

**程序二** :

```
// Java program to demonstrate the isAfter() method

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

        // prints the time1
        System.out.println("time1: "
                           + time1);

        // prints the time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 is after time2: "
                           + time1.isAfter(time2));
    }
}
```

**输出:**

```
time1: 15:30:30+07:00
time1: 15:30:30+07:00
time1 is after time2: false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # isaafter-Java . time . offsettime-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#isAfter-java.time.OffsetTime-)
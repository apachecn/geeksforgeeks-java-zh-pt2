# Java 中()方法的偏移量，示例

> 原文:[https://www . geeksforgeeks . org/offsettime-of-in-Java-method-in-with-examples/](https://www.geeksforgeeks.org/offsettime-of-method-in-java-with-examples/)

Java 中 **OffsetTime** 类的**(int hour，int minute，int second，int 纳秒，ZoneOffset offset)** 方法用于根据传递的小时、分钟、秒和纳秒值创建 **OffsetTime** 的实例。在这种方法中，我们以整数的形式传递小时、分钟、秒和纳秒的值，它根据这些值返回时间作为**偏移时间**。

**语法:**

```
public static OffsetTime of(int hour,
                            int minute,
                            int second,
                            int nanosecond,
                            ZoneOffset offset)

```

**参数:**该方法接受五个参数:

*   **小时**–代表一天中的小时。从 0 到 23 不等。
*   **分钟**–表示一小时中的分钟。从 0 到 59 不等。
*   **秒**–它代表一分钟中的第二秒。从 0 到 59 不等。
*   **纳秒**–代表秒的纳米。它从 0 到 999999999 不等。
*   **偏移**–表示区域偏移。它不应为空。

**返回值:**这个方法总是返回**偏置时间**。

**异常:**如果任何参数值超出范围，该方法抛出**日期时间异常**。

下面的程序说明了 Java 中 OffsetTime 类的()方法:

**程序 1:**

```
// Java program to demonstrate
// OffsetTime of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create OffsetTime object
        OffsetTime offsettime
            = OffsetTime.of(
                8, 20, 40, 50000,
                ZoneOffset.UTC);

        // Print time
        System.out.println(
            "TIME: "
            + offsettime);
    }
}
```

**Output:**

```
TIME: 08:20:40.000050Z

```

**程序 2:**

```
// Java program to demonstrate
// OffsetTime of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create OffsetTime object
        OffsetTime offsettime
            = OffsetTime.of(
                5, 40, 30, 20000,
                ZoneOffset.MIN);

        // Print time
        System.out.println("TIME: "
                           + offsettime);
    }
}
```

**Output:**

```
TIME: 05:40:30.000020-18:00

```

**程序 3:**

```
// Java program to demonstrate
// OffsetTime of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create OffsetTime object
        OffsetTime offsettime
            = OffsetTime.of(
                6, 10, 20, 30000,
                ZoneOffset.MAX);

        // Print time
        System.out.println("TIME: "
                           + offsettime);
    }
}
```

**Output:**

```
TIME: 06:10:20.000030+18:00

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsettime . html # of(int，int，int，int，int，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetTime.html#of(int, int, int, int, java.time.ZoneOffset))
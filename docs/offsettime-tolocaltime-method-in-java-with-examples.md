# Java 中 OffsetTime toLocalTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-tolocaltime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-tolocaltime-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **toLocalTime()** 方法获取这个日期时间的 LocalTime 部分。

**语法:**

```java
public LocalTime toLocalTime()

```

**参数:**该方法不接受任何参数。

**返回值:**它返回一个本地时间，其小时、分钟、秒和纳秒与该日期时间相同。

下面的程序举例说明了 toLocalTime()方法:

```java
// Java program to demonstrate the toLocalTime() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Gets the current time
        OffsetTime time = OffsetTime.now();

        // Gets the local time
        System.out.println("Local-time: " + time.toLocalTime());
    }
}
```

**输出:**

```java
Local-time: 03:59:10.258

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # to localtime–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#toLocalTime--)
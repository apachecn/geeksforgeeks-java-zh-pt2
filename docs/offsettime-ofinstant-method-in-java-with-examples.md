# Java 中 OffsetTime ofInstant()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-of instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-ofinstant-method-in-java-with-examples/)

**偏移设置类**的 **ofInstant()** 方法用于从作为参数传递的即时和区域标识中获取偏移设置的实例。在这种方法中，首先，从世界协调时/格林威治时间的偏移是使用区域标识和瞬间获得的。然后，从瞬间和偏移计算出当地时间。

**语法:**

```java
public static OffsetTime 
       ofInstant(Instant instant, ZoneId zone)

```

**参数:**此方法接受两个参数:

*   **Moment** : It is the moment when the OffsetTime object is created. It should not be empty.
*   **Area** : It is an area with a specified time. It should not be empty.

**返回值:**该方法返回从传递的瞬间创建的**偏移时间对象**。

下面的程序举例说明了 Instant()方法:

```java
// Java program to demonstrate
// OffsetTime.ofInstant() method

import java.time.OffsetTime;
import java.time.Instant;
import java.time.ZoneId;

public class GFG {
    public static void main(String[] args)
    {
        // Creates an instance
        OffsetTime time = OffsetTime.ofInstant(Instant.now(), 
                                       ZoneId.systemDefault());

        System.out.println("Offset time: " + time);
    }
}
```

**输出:**

```java
Offset time: 03:17:43.019Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # of instant-Java . time . instant-Java . time . zoneid-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#ofInstant-java.time.Instant-java.time.ZoneId-)
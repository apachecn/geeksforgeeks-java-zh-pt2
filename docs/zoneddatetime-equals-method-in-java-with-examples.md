# Java 中的 ZonedDateTime 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-equals-method-in-java-with-examples/)

Java 中 **ZonedDateTime** 类的 **equals()** 方法用于将这个 ZonedDateTime 与作为参数传递的另一个日期时间对象进行比较。比较基于偏移日期时间和区域。只有 ZonedDateTime 类型的对象相互比较，其他类型返回 false。此方法返回的值确定如下:

*   如果两个 ZonedDateTime 相等，则返回 true。
*   如果两个 ZonedDateTime 不相等，则返回 false。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受单个参数**对象**，该参数表示要与该区域数据时间进行比较的对象。这是一个强制参数，不应为空。

**返回值:**如果两个区域时间相等，则该方法返回**真**假。

下面的程序说明了 equals()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZonedDateTime objects
        ZonedDateTime zoneddatetime1
            = ZonedDateTime.parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        ZonedDateTime zoneddatetime2
            = ZonedDateTime.parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // apply equals()
        boolean value = zoneddatetime1.equals(zoneddatetime2);

        // print result
        System.out.println("Both ZonedDateTime are equal: " + value);
    }
}
```

**Output:**

```java
Both ZonedDateTime are equal: true

```

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZonedDateTime objects
        ZonedDateTime zoneddatetime1
            = ZonedDateTime.parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        ZonedDateTime zoneddatetime2
            = ZonedDateTime.parse("2018-12-16T20:28:33.213+05:30[Asia/Calcutta]");

        // apply equals()
        boolean value = zoneddatetime1.equals(zoneddatetime2);

        // print result
        System.out.println("Both ZonedDateTime are equal: " + value);
    }
}
```

**Output:**

```java
Both ZonedDateTime are equal: false

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#equals(java.lang.Object))
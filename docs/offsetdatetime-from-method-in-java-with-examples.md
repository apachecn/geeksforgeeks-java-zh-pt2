# Java 中 OffsetDateTime from()方法，示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-from-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **from()** 方法从时态对象中获取 OffsetDateTime 的一个实例。
**语法:**

```java
public static OffsetDateTime from(TemporalAccessor temporal)
```

**参数:**该方法接受单个参数**时态**，指定要转换的时态对象，不为空。
**返回值:**返回本地日期，不为空。
**异常**:函数抛出**日期时间异常**，即无法转换为偏置日期时间。
以下程序说明了*从()*方法:
**程序 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the from() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Function used
        OffsetDateTime date = OffsetDateTime.from(ZonedDateTime.now());

        // Prints the date
        System.out.println(date);
    }
}
```

**Output:** 

```java
2018-12-12T08:24:12.442Z
```

**节目 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the from() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Function used
        OffsetDateTime date = OffsetDateTime.from(ZonedDateTime.now());

        // Prints the date
        System.out.println(date);
    }
}
```

**Output:** 

```java
2018-12-12T08:24:15.077Z
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#from-java.time.temporal.TemporalAccessor-)
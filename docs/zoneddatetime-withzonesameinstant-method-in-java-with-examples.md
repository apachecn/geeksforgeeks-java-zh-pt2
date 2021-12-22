# 带有区域的区域时间 Java 中的区域时间()方法，示例

> 原文:[https://www . geeksforgeeks . org/zone ddatetime-with zone same instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withzonesameinstant-method-in-java-with-examples/)

**ZonedDateTime** 类的**with zonesametime()**方法用于通过更改时区返回该 ZonedDateTime 对象的副本，但不返回即时消息。这种方法基于保持相同的瞬间，因此局部时间线中的间隙和重叠对结果没有影响。

**语法:**

```java
public ZonedDateTime withZoneSameInstant(ZoneId zone)
```

**参数:**此方法接受一个单参数**区域**时区更改为。它不应为空。

**返回值:**该方法根据请求区域的日期时间返回一个**区域日期时间**。

**异常抛出:** **日期时间异常**如果结果超出支持的日期范围。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ZonedDateTime.withZoneSameInstant() method

// Importing required classes
import java.time.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a ZonedDateTime object
        ZonedDateTime zonedDT = ZonedDateTime.parse(
            "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Printing ZonedDateTime of Calcutta on console
        System.out.println("ZonedDateTime of Calcutta: "
                           + zonedDT);

        // Applying withZoneSameInstant()
        ZonedDateTime zonedDT2
            = zonedDT.withZoneSameInstant(
                ZoneId.of("Pacific/Fiji"));

        // Now printing ZonedDateTime of Fuji
        // after withZoneSameInstant()
        System.out.println("ZonedDateTime of Fuji: "
                           + zonedDT2);
    }
}
```

**Output:** 

```java
ZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime of Fuji: 2018-12-07T02:51:12.123+13:00[Pacific/Fiji]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Demonstrate
// ZonedDateTime.withZoneSameInstant() method

// Importing required classes
import java.time.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a ZonedDateTime object and
        // pasing date and time of Europe/Paris
        ZonedDateTime zonedDT = ZonedDateTime.parse(
            "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // Printing ZonedDateTime of Paris on console
        // before applying withZoneSameInstant() method
        System.out.println("ZonedDateTime of Paris: "
                           + zonedDT);

        // Now applying withZoneSameInstant() method
        ZonedDateTime zonedDT2
            = zonedDT.withZoneSameInstant(
                ZoneId.of("Canada/Yukon"));

        // Printing ZonedDateTime
        // after applying withZoneSameInstant()
        System.out.println("ZonedDateTime of Yukon: "
                           + zonedDT2);
    }
}
```

**Output**

```java
ZonedDateTime of Paris: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ZonedDateTime of Yukon: 2018-10-25T14:12:31.123-07:00[Canada/Yukon]
```
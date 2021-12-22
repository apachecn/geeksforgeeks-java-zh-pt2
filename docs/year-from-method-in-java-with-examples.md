# Java 中的 Year from()方法，带示例

> 原文:[https://www . geesforgeks . org/year-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-from-method-in-java-with-examples/)

**from()** 方法的 **Year** 类用于从作为参数传递的临时处理器对象中获取 Year 实例。临时日历表示一组任意的日期和时间信息，这种方法有助于根据指定的临时日历对象获取年份对象。

**语法:**

```java
public static Year from(TemporalAccessor temporal)

```

**参数:**该方法接受**时态**作为参数，该参数是时态对象。它不应为空。

**返回值:**此方法返回年份对象。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法转换为年份。

以下程序说明了 from()方法:
**程序 1:**

```java
// Java program to demonstrate
// Year.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a temporal object
        LocalDate date = LocalDate.parse("2007-12-03");

        // print instance
        System.out.println("LocalDate :"
                           + date);

        // apply from method of Year class
        Year year = Year.from(date);

        // print instance
        System.out.println("Year get from"
                           + " method: "
                           + year);
    }
}
```

**Output:**

```java
LocalDate :2007-12-03
Year get from method: 2007

```

**程序 2:**

```java
// Java program to demonstrate
// Year.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a temporal object
        LocalDate ins = LocalDate.parse("2018-11-27");

        // print instance
        System.out.println("LocalDate :"
                           + ins);

        // apply from method of Year class
        Year year = Year.from(ins);

        // print instance
        System.out.println("Year get from"
                           + " method: "
                           + year);
    }
}
```

**Output:**

```java
LocalDate :2018-11-27
Year get from method: 2018

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # from(Java . time . temporal . temporal)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#from(java.time.temporal.Temporal))
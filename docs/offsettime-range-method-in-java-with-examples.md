# Java 中的 OffsetTime range()方法，示例

> 原文:[https://www . geeksforgeeks . org/offsettime-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-range-method-in-java-with-examples/)

**范围()**偏移时间**类的**方法，用于获取作为参数传递给该方法的字段的最小值和最大值的范围。此方法的返回值是该字段的 ValueRange 对象，并且该方法只为 OffsetTime 对象支持的那些字段返回 ValueRange 对象。所以当这个方法不支持这个字段时，这个方法就会抛出一个异常。

**语法:**

```java
public ValueRange range(TemporalField field)

```

**参数:**该方法接受一个参数字段，即查询范围的字段。

**返回值:**此方法返回字段的有效值范围。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得字段的范围。
*   **unsupportedtemporaltypexception**–如果不支持该字段。

以下程序举例说明了 range()方法:
**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create OffsetTime objects
        OffsetTime offset
            = OffsetTime
                  .parse("15:30:30+07:00");

        // apply range() method of OffsetTime class
        ValueRange result
            = offset.range(ChronoField.OFFSET_SECONDS);

        // print results
        System.out.println("Range in OFFSET_SECONDS: "
                           + result);
    }
}
```

**Output:**

```java
Range in OFFSET_SECONDS: -64800 - 64800

```

**程序 2:**

```java
// Java program to demonstrate
// OffsetTime.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create OffsetTime objects
        OffsetTime offset
            = OffsetTime
                  .parse("15:30:30+07:00");

        // apply range() method of OffsetTime class
        ValueRange result
            = offset.range(ChronoField.SECOND_OF_MINUTE);

        // print results
        System.out.println("Range in SECOND_OF_MINUTE: "
                           + result);
    }
}
```

**Output:**

```java
Range in SECOND_OF_MINUTE: 0 - 59

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsettime . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetTime.html#range(java.time.temporal.TemporalField))
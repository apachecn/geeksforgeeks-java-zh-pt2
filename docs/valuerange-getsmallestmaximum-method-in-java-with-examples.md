# Java 中的 ValueRange getSmallestMaximum()方法，带示例

> 原文:[https://www . geesforgeks . org/value range-getsmallest max-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-getsmallestmaximum-method-in-java-with-examples/)

**ValueRange 类**的 **getSmallestMaximum()** 方法用于获取 ValueRange 可以取的最小可能最大值。例如，年月日始终在 28 到 31 天之间。因此，最小最大值为 28。

**语法:**

```java
public long getSmallestMaximum()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该值域的最小可能最大值。

下面的程序说明了 ValueRange.getSmallestMaximum()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.getSmallestMaximum() method

import java.time.LocalDateTime;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create LocalDateTime
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-02-06T19:21:12");

        // Get ValueRange object
        ValueRange vR
            = l1.range(ChronoField.DAY_OF_MONTH);

        // apply getSmallestMaximum()
        long sMax = vR.getSmallestMaximum();

        // print results
        System.out.println("Smallest Maximum "
                           + "for DAY_OF_MONTH: "
                           + sMax);
    }
}
```

**Output:**

```java
Smallest Maximum for DAY_OF_MONTH: 28

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.getSmallestMaximum() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 99999);

        // get smallest Maximum value
        long smax = vRange.getSmallestMaximum();

        // print results
        System.out.println("smallest maximum : "
                           + smax);
    }
}
```

**Output:**

```java
smallest maximum : 99999

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # getSmallestMaximum()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#getSmallestMaximum())
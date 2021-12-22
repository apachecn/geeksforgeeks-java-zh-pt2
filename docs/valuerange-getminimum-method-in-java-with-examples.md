# Java 中的 ValueRange getMinimum()方法，示例

> 原文:[https://www . geesforgeks . org/value range-get minimum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-getminimum-method-in-java-with-examples/)

**值域类**的 **getMinimum()** 方法用于获取值域可以取的最小值。例如，时间字段星期几总是从 1 开始。因此最小值为 1。

**语法:**

```java
public long getMinimum()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该值域的最小值。

下面的程序说明了 ValueRange.getMinimum()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.getMinimum() method

import java.time.LocalDateTime;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create LocalDateTime
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-12-06T19:21:12");

        // Get ValueRange object
        ValueRange vR
            = l1.range(ChronoField.DAY_OF_WEEK);

        // apply getMinimum()
        long min = vR.getMinimum();

        // print results
        System.out.println("Minimum for DAY_OF_WEEK: "
                           + min);
    }
}
```

**Output:**

```java
Minimum for DAY_OF_WEEK: 1

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.getMinimum() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 99999);

        // get Largest minimum
        long min = vRange.getMinimum();

        // print results
        System.out.println("Minimum : "
                           + min);
    }
}
```

**Output:**

```java
Minimum : 1111

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # getMinimum()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#getMinimum())
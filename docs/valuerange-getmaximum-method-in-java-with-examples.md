# Java 中的 ValueRange getMaximum()方法，示例

> 原文:[https://www . geesforgeks . org/value range-get maximum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-getmaximum-method-in-java-with-examples/)

**ValueRange 类**的 **getMaximum()** 方法用于获取 ValueRange 可以取的最大值。例如，时间域星期几总是在 7 点结束。因此，最大值为 7。

**语法:**

```
public long getMaximum()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该值域的最大值。

下面的程序说明了 ValueRange.getMaximum()方法:
**程序 1:**

```
// Java program to demonstrate
// ValueRange.getMaximum() method

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

        // apply getMaximum()
        long maximum = vR.getMaximum();

        // print results
        System.out.println("Maximum for DAY_OF_WEEK: "
                           + maximum);
    }
}
```

**Output:**

```
Maximum for DAY_OF_WEEK: 7

```

**程序 2:**

```
// Java program to demonstrate
// ValueRange.getMaximum() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 99999);

        // get Maximum value using getMaximum()
        long max = vRange.getMaximum();

        // print results
        System.out.println("Maximum : "
                           + max);
    }
}
```

**Output:**

```
Maximum : 99999

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # getMaximum()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#getMaximum())
# Java 中的 ValueRange getLargestMinimum()方法，示例

> 原文:[https://www . geesforgeks . org/value range-getlargestminium-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-getlargestminimum-method-in-java-with-examples/)

**值域类**的 **getLargestMinimum()** 方法用于获取值域可以取的最大可能最小值。例如，时间字段星期几总是从 1 开始。因此最大最小值为 1。

**语法:**

```
public long getLargestMinimum()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回此值范围的最大可能最小值。

下面的程序说明了 ValueRange.getLargestMinimum()方法:
**程序 1:**

```
// Java program to demonstrate
// ValueRange.getLargestMinimum() method

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

        // apply getLargestMinimum()
        long Lmin = vR.getLargestMinimum();

        // print results
        System.out.println("Largest Minimum "
                           + "for DAY_OF_WEEK: "
                           + Lmin);
    }
}
```

**Output:**

```
Largest Minimum for DAY_OF_WEEK: 1

```

**程序 2:**

```
// Java program to demonstrate
// ValueRange.getLargestMinimum() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 99999);

        // get Largest minimum
        long Lmin = vRange.getLargestMinimum();

        // print results
        System.out.println("Largest Minimum : "
                           + Lmin);
    }
}
```

**Output:**

```
Largest Minimum : 1111

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # getLargestMinimum()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#getLargestMinimum())
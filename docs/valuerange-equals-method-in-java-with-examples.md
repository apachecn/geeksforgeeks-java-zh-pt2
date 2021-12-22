# Java 中的 ValueRange 等于()方法，示例

> 原文:[https://www . geesforgeks . org/value range-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-equals-method-in-java-with-examples/)

**值范围类**的**等于()**方法用于检查该值范围是否等于另一个值范围，其中另一个值范围作为参数传递给该方法。比较基于四个值，即最小值、最大值、最小值、最大值和最大值。

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该方法接受**对象**，该对象为检查对象。

**返回值:**如果等于另一个范围，则该方法返回 true。

下面的程序说明了 ValueRange.equals()方法:
**程序 1:**

```
// Java program to demonstrate
// ValueRange.equals() method

import java.time.LocalDateTime;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create LocalDateTime
        LocalDateTime l1
            = LocalDateTime
                  .parse("2020-10-06T08:21:14");
        LocalDateTime l2
            = LocalDateTime
                  .parse("2019-12-26T08:21:14");

        // Get ValueRange object
        ValueRange vR1
            = l1.range(ChronoField.DAY_OF_MONTH);
        ValueRange vR2
            = l2.range(ChronoField.DAY_OF_MONTH);

        // apply equals()
        boolean response = vR1.equals(vR2);

        // print results
        System.out.println("Both ValueRange are equal: "
                           + response);
    }
}
```

**Output:**

```
Both ValueRange are equal: true

```

**程序 2:**

```
// Java program to demonstrate
// ValueRange.equals() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange objects
        ValueRange vRange = ValueRange.of(1111, 66666);
        ValueRange OtherVRange = ValueRange.of(111, 66666);

        // apply equals()
        boolean response = vRange.equals(OtherVRange);

        // print results
        System.out.println("Both ValueRange are equal: "
                           + response);
    }
}
```

**Output:**

```
Both ValueRange are equal: false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#equals(java.lang.Object))
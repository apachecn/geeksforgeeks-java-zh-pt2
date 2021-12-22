# ValueRange 是 Java 中的 ValidValue()方法，带示例

> 原文:[https://www . geesforgeks . org/value range-is valid value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/valuerange-isvalidvalue-method-in-java-with-examples/)

**值范围类**的**是有效值()**方法，用于检查作为参数传递的值是否在有效范围内。此方法验证该值是否在存储的值范围内。

**语法:**

```
public boolean isValidValue(long value)

```

**参数:**该方法接受**值**，该值是要检查的值。

**返回值:**如果该值有效，则该方法返回真。

下面的程序说明了 ValueRange.isValidValue()方法:
**程序 1:**

```
// Java program to demonstrate
// ValueRange.isValidValue() method

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

        // Get ValueRange object
        ValueRange vR
            = l1.range(ChronoField.DAY_OF_MONTH);

        // apply isValidValue()
        boolean response = vR.isValidValue(12);

        // print results
        System.out.println("isValidValue: "
                           + response);
    }
}
```

**Output:**

```
isValidValue: true

```

**程序 2:**

```
// Java program to demonstrate
// ValueRange.isValidValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 66666);

        // apply isValidValue()
        boolean response = vRange.isValidValue(12);

        // print results
        System.out.println("isValidValue: "
                           + response);
    }
}
```

**Output:**

```
isValidValue: false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # isvalid value(长)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#isValidValue(long))
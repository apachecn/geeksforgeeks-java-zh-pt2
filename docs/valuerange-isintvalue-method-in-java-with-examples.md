# ValueRange 是 Java 中的值()方法，示例

> 原文:[https://www . geesforgeks . org/value range-is intvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-isintvalue-method-in-java-with-examples/)

**值域类**的**IsinVaLue()**方法用于检查值域中的所有值是否符合 int。此方法验证所有有效值是否在整数范围内。

**语法:**

```
public boolean isIntValue()

```

**参数:**此方法不接受任何内容。

**返回值:**如果一个有效值总是符合一个整数，这个方法返回真。

下面的程序说明了 ValueRange.isIntValue()方法:
**程序 1:**

```
// Java program to demonstrate
// ValueRange.isIntValue() method

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
            = l1.range(ChronoField.DAY_OF_MONTH);

        // apply isIntValue()
        boolean response = vR.isIntValue();

        // print results
        System.out.println("isIntValue: "
                           + response);
    }
}
```

**Output:**

```
isIntValue: true

```

**程序 2:**

```
// Java program to demonstrate
// ValueRange.isIntValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 66666);

        // apply isIntValue()
        boolean response = vRange.isIntValue();

        // print results
        System.out.println("isIntValue: "
                           + response);
    }
}
```

**Output:**

```
isIntValue: true

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # IsintVaLue()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#isIntValue())
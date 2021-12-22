# ValueRange 是 Java 中的一个 ValidIntValue()方法，示例

> 原文:[https://www . geesforgeks . org/value range-isvalintvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-isvalidintvalue-method-in-java-with-examples/)

**值范围类**的**是有效值()**方法，用于检查作为参数传递的值是否在有效范围内。此方法还验证该范围内的所有值都符合 int。

**语法:**

```java
public boolean isValidIntValue(long value)

```

**参数:**该方法接受**值**，该值是要检查的值。

**返回值:**如果该值有效且符合整数，则该方法返回真。

下面的程序说明了 ValueRange.isValidIntValue()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.isValidIntValue() method

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

        // apply isValidIntValue()
        boolean response = vR.isValidIntValue(30);

        // print results
        System.out.println("isValidIntValue: "
                           + response);
    }
}
```

**Output:**

```java
isValidIntValue: true

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.isValidIntValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 66666);

        // apply isValidIntValue()
        boolean response = vRange.isValidIntValue(333);

        // print results
        System.out.println("isValidIntValue: "
                           + response);
    }
}
```

**Output:**

```java
isValidIntValue: false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # isValidIntValue()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#isValidIntValue())
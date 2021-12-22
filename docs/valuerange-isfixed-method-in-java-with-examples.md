# ValueRange 是 Java 中的 Fixed()方法，带有示例

> 原文:[https://www . geesforgeks . org/value range-is fixed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-isfixed-method-in-java-with-examples/)

**值域类**的**是固定的()**方法，用于检查值域是否固定且完全已知。例如，月日计时从 1 运行到 28 和 31 之间。月日最大值不固定，存在不确定性。然而，对于 12 月，范围总是 1 到 31，因此它是固定的。

**语法:**

```java
public boolean isFixed()

```

**参数:**此方法不接受任何内容。

**返回值:**如果这组值是固定的，则该方法返回 true。

下面的程序说明了 ValueRange.isFixed()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.isFixed() method

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

        // apply isFixed()
        boolean response = vR.isFixed();

        // print results
        System.out.println("isFixed: "
                           + response);
    }
}
```

**Output:**

```java
isFixed: true

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.isFixed() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 66666);

        // apply isFixed()
        boolean response = vRange.isFixed();

        // print results
        System.out.println("isFixed: "
                           + response);
    }
}
```

**Output:**

```java
isFixed: true

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # IsFixed()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#isFixed())
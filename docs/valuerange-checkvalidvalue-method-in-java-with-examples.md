# Java 中的 ValueRange checkValidValue()方法，示例

> 原文:[https://www . geesforgeks . org/value range-checkvalidvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-checkvalidvalue-method-in-java-with-examples/)

**ValueRange 类**的 **checkValidValue()** 方法用于检查作为参数传递的值是否有效。作为参数传递的字段仅用于改善错误消息。此方法检查传递的值是否在 ValueRange 中。

**语法:**

```
public long checkValidValue(long value, TemporalField field)

```

**参数:**该方法接受两个参数:

*   **值**是要检查的值
*   **范围**是被检查的字段。

**返回值:**这个方法返回传入的值。

下面的程序说明了 ValueRange.checkValidValue()方法:
**程序 1:**

```
// Java program to demonstrate
// ValueRange.checkValidValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1, 10000);

        // check value 4999 in range or not
        long value1 = vRange.checkValidValue(4999, null);

        // print
        System.out.println("Value passed :" + value1);
    }
}
```

**Output:**

```
Value passed :4999

```

**程序 2:**

```
// Java program to demonstrate
// ValueRange.checkValidValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 99999);

        // check value 6666 in range or not
        long value1 = vRange.checkValidValue(6666, null);

        // print
        System.out.println("Value passed :" + value1);
    }
}
```

**Output:**

```
Value passed :6666

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # checkValidValue(long，Java . time . temporal . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#checkValidValue(long, java.time.temporal.TemporalField))
# Java 中的 ValueRange checkValidIntValue()方法，示例

> 原文:[https://www . geesforgeks . org/value range-checkvalidintvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-checkvalidintvalue-method-in-java-with-examples/)

**值范围类**的 **checkValidIntValue()** 方法用于检查作为参数传递的值是否有效以及是否符合整数。此方法验证作为参数传递的值是否在有效的值范围内。对于此方法，方法返回的值是否适合 int 很重要。作为参数传递的字段仅用于改善错误消息。

**语法:**

```java
public int checkValidIntValue(long value, TemporalField field)

```

**参数:**该方法接受两个参数:

*   **值**是要检查的值
*   **范围**是被检查的字段，可以为空。

**返回值:**这个方法返回传入的值。

下面的程序说明了 ValueRange.checkValidIntValue()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.checkValidIntValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1, 10000);

        // check value 500 in range or not
        int value1 = vRange.checkValidIntValue(500, null);

        // print
        System.out.println("Value passed :" + value1);
    }
}
```

**Output:**

```java
Value passed :500

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.checkValidIntValue() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(10000, 99999);

        // check value 44444 in range or not
        int value1 = vRange.checkValidIntValue(44444, null);

        // print
        System.out.println("Value passed :" + value1);
    }
}
```

**Output:**

```java
Value passed :44444

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # checkValidIntValue(long，Java . time . temporal . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#checkValidIntValue(long, java.time.temporal.TemporalField))
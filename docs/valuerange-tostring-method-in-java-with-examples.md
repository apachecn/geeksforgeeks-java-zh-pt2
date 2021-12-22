# Java 中的 ValueRange toString()方法，带示例

> 原文:[https://www . geesforgeks . org/value range-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-tostring-method-in-java-with-examples/)

**ValueRange 类**的 **toString()** 方法用于将该 ValueRange 作为字符串返回，格式为“{ min }/{ largestMin }–{ small estMax }/{ max } '，其中如果与 min 或 max 相同，则可以省略 large stmin 或 smallestMax 部分以及关联的斜杠。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该范围的字符串表示形式，不为空。

下面的程序说明了 ValueRange.toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.toString() method

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

        // print results using toString()
        System.out.println("ValueRange: "
                           + vR.toString());
    }
}
```

**Output:**

```java
ValueRange: 1 - 31

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.toString() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 66666);

        // print results using toString()
        System.out.println("ValueRange: "
                           + vRange.toString());
    }
}
```

**Output:**

```java
ValueRange: 1111 - 66666

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#toString())
# Java 中的 ValueRange hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/value range-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/valuerange-hashcode-method-in-java-with-examples/)

**值域类**的 **hashCode()** 方法用于获取该值域的 hashCode 值。它返回一个整数值，该整数值是 ValueRange 实例的 hashCode 值。

**语法:**

```java
public int hashCode()

```

**参数:**
这个方法什么都不接受。

**返回值:**
这个方法返回一个合适的哈希码。

下面的程序说明了 ValueRange.hashCode()方法:
**程序 1:**

```java
// Java program to demonstrate
// ValueRange.hashCode() method

import java.time.LocalDateTime;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create LocalDateTime
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-02-06T19:21:12");

        // Get ValueRange object
        ValueRange vR
            = l1.range(ChronoField.DAY_OF_MONTH);

        // apply hashCode()
        int code = vR.hashCode();

        // print results
        System.out.println("hashCode: "
                           + code);
    }
}
```

**Output:**

```java
hashCode: 1900573

```

**程序 2:**

```java
// Java program to demonstrate
// ValueRange.hashCode() method

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create ValueRange object
        ValueRange vRange = ValueRange.of(1111, 66666);

        // apply hashCode()
        int code = vRange.hashCode();

        // print results
        System.out.println("hashCode: "
                           + code);
    }
}
```

**Output:**

```java
hashCode: 3932210

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/value range . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ValueRange.html#hashCode())
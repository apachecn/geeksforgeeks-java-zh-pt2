# Java 中的 OffsetDateTime withNano()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-with nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withnano-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withNano()** 方法返回这个 OffsetDateTime 的一个副本，按照参数中的指定更改了纳米秒。

**语法:**

```
public OffsetDateTime withNano(int nanoOfSecond)
```

**参数:**此方法接受单个参数 **nanaOfSecond** ，该参数指定要在结果中设置的纳米秒，范围从 0 到 999，999，999..

**返回值:**返回基于该日期的偏移日期时间，请求的单位为秒，不为空。

**异常**:当纳秒值无效时，程序抛出**日期时间异常**。

以下程序举例说明了 *withNano()* 方法:

**程序 1:**

```
// Java program to demonstrate the withNano() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse(
                      "2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Changes the nano-of-second
        System.out.println("Date1 after altering nano-of-second: "
                           + date1.withNano(1000));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering nano-of-second: 2018-12-12T13:30:30.000001+05:00

```

**程序二:**

```
// Java program to demonstrate the withNano() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        try {

            // Parses the date1
            OffsetDateTime date1
                = OffsetDateTime
                      .parse(
                          "2018-12-12T13:30:30+05:00");

            // Prints dates
            System.out.println("Date1: " + date1);

            // Changes the nano-of-second
            System.out.println("Date1 after altering nano-of-second: "
                               + date1.withNano(1000000000));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Exception: java.time.DateTimeException: 
           Invalid value for NanoOfSecond (valid values 0 - 999999999): 1000000000

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with nano(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withNano(int))
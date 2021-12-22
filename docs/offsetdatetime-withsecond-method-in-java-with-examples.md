# Java 中的 OffsetDateTime withSecond()方法，示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-with second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withsecond-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withSecond()** 方法返回这个 OffsetDateTime 的一个副本，其中的分钟数按照参数中的指定进行了更改。

**语法:**

```
public OffsetDateTime withSecond(int second)
```

**参数:**该方法接受单个参数**秒**，该参数指定要在结果中设置的分钟秒，范围从 0 到 59。

**返回值:**返回基于该日期的偏移日期时间，请求的分钟数不为空。

**异常**:当分钟秒数值无效时，程序抛出**日期时间异常**。

以下程序说明了*带秒()*的方法:

**程序 1:**

```
// Java program to demonstrate the withSecond() method

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

        // Changes the second-of-minute
        System.out.println("Date1 after altering second-of-minute: "
                           + date1.withSecond(40));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering second-of-minute : 2018-12-12T13:30:40+05:00

```

**程序二:**

```
// Java program to demonstrate the withSecond() method

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

            // Changes the second-of-minute
            System.out.println("Date1 after altering second-of-minute: "
                               + date1.withSecond(70));
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
           Invalid value for SecondOfMinute (valid values 0 - 59): 70

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with second(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withSecond(int))
# Java 中的 ZonedDateTime 查询()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-query-method-in-java-with-examples/)

**query()** 一个 **ZonedDateTime** 类的方法，用于使用指定的查询作为参数来查询这个 ZonedDateTime。作为参数传递的临时查询对象定义了用于从该区域数据时间获取结果的逻辑。

**语法:**

```java
public <R> R query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If you can't query.
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 query()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZonedDateTime object
        ZonedDateTime zlt
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // apply the query method of ZonedDateTime class
        String value
            = zlt.query(
                     TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value"
                           + " for ZonedDateTime is "
                           + value);
    }
}
```

**输出:**

```java
Precision value for ZonedDateTime is Nanos

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZonedDateTime object
        ZonedDateTime zlt
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // apply query method of ZonedDateTime class
        // print the result
        System.out.println("offset value for "
                           + "ZonedDateTime is "
                           + zlt.query(
                                 TemporalQueries.offset()));
    }
}
```

**输出:**

```java
offset value for ZonedDateTime is +02:00

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # query(Java . time . temporal query)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#query(java.time.temporal.TemporalQuery))
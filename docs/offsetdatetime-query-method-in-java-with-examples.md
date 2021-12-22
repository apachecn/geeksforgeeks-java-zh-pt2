# Java 中的 OffsetDateTime 查询()方法，示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-query-method-in-java-with-examples/)

**query()** 一个 **OffsetDateTime** 类的方法，用于使用指定的查询作为参数来查询这个 OffsetDateTime。作为参数传递的 TemporalQuery 对象定义了用于从这个 OffsetDateTime 获取结果的逻辑。

**语法:**

```
public <R> R query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If you can't query.
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 query()方法:

**程序 1:**

```
// Java program to demonstrate
// OffsetDateTime.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create OffsetDateTime object
        OffsetDateTime olt
            = OffsetDateTime.parse(
                "2018-12-12T13:30:30+05:00");

        // apply query method of OffsetDateTime class
        String value
            = olt.query(
                     TemporalQueries.precision())
                  .toString();

        // print the result
        System.out.println("Precision value"
                           + " for OffsetDateTime is "
                           + value);
    }
}
```

**输出:**

```
Precision value for OffsetDateTime is Nanos

```

**程序二:**

```
// Java program to demonstrate
// OffsetDateTime.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create OffsetDateTime object
        OffsetDateTime olt
            = OffsetDateTime.parse(
                "2018-12-12T13:30:30+05:00");

        // apply query method of
        // OffsetDateTime class
        // print the result
        System.out.println("offset value "
                           + "for OffsetDateTime is "
                           + olt.query(
                                 TemporalQueries.offset()));
    }
}
```

**输出:**

```
offset value for OffsetDateTime is +05:00

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # query(Java . time . temporal . temporal query)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#query(java.time.temporal.TemporalQuery))
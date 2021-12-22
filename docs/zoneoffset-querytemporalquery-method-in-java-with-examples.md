# Java 中的 ZoneOffset 查询(TemporalQuery)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-query temporal query-Java 中的方法-示例/](https://www.geeksforgeeks.org/zoneoffset-querytemporalquery-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的**查询(TemporalQuery)** 方法用于使用作为参数传递的 TemporalQuery 执行对此 ZoneOffset 的查询。此方法以指定类型的形式返回查询结果。

**语法:**

```
public <R> R query(TemporalQuery<R> temporalQuery)

```

**参数:**该方法接受一个参数**临时查询**，该参数是要在该区域偏移上执行的查询。

**返回值:**该方法返回指定查询的 **R 型**查询结果。

**异常:**此方法抛出:

*   **Abnormal date and time** : If you can't query (defined by query).
*   **Arithmetic exception** : If there is a numerical overflow (defined by the query).

以下示例说明了 ZoneOffset.query()方法:

**例 1:**

```
// Java code to illustrate query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");
        System.out.println("ZoneOffset: "
                           + zoneOffset);

        // Using query() method
        System.out.println("Offset value: "
                           + zoneOffset.query(TemporalQueries.offset()));
    }
}
```

**输出:**

```
ZoneOffset: +05:30
Offset value: +05:30

```

**例 2:**

```
// Java code to illustrate query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");
        System.out.println("ZoneOffset: "
                           + zoneOffset);

        // Using query() method
        System.out.println("Zone value: "
                           + zoneOffset.query(TemporalQueries.zone()));
    }
}
```

**输出:**

```
ZoneOffset: Z
Zone value: Z

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#query-java.time.temporal.TemporalQuery-)
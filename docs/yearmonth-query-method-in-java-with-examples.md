# Java 中的年月查询()方法，示例

> 原文:[https://www . geesforgeks . org/year-month-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-query-method-in-java-with-examples/)

**query()** 一个 **YearMonth** 类的方法，使用指定的查询作为参数来查询这个 YearMonth。作为参数传递的 TemporalQuery 对象定义了用于获取该年月结果的逻辑。

**语法:**

```java
public <R> R query(TemporalQuery<R> query)

```

**参数:**该方法只接受一个参数**查询**，即要调用的查询。

**返回值:**该方法返回查询结果，可能返回 null。

**异常:**
此方法抛出以下异常:

*   **日期时间异常**–如果无法查询。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了查询()的方法:
**程序 1:**

```java
// Java program to demonstrate
// YearMonth.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create YearMonth object
        YearMonth yM = YearMonth.of(2020, 12);

        // apply query method of YearMonth class
        String value = yM.query(TemporalQueries
                                    .precision())
                           .toString();

        // print the result
        System.out.println("Precision value"
                           + " for YearMonth is "
                           + value);
    }
}
```

**Output:**

```java
Precision value for YearMonth is Months

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```java
// Java program to demonstrate
// YearMonth.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create YearMonth object
        YearMonth YM = YearMonth.of(2019, 3);

        // apply query method of YearMonth class
        // print the result
        System.out.println("Zone value for YearMonth is "
                           + YM.query(
                                 TemporalQueries.offset()));
    }
}
```

**Output:**

```java
Zone value for YearMonth is null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # query(Java . time . temporal . temporal query)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#query(java.time.temporal.TemporalQuery))
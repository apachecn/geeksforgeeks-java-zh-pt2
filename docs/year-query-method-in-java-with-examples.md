# Java 年查询()方法，带示例

> 原文:[https://www . geesforgeks . org/year-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-query-method-in-java-with-examples/)

**查询() **Year** 类的**方法，用于使用指定的查询作为参数查询该 Year。作为参数传递的临时查询对象定义了用于获取今年结果的逻辑。

**语法:**

```
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

```
// Java program to demonstrate
// Year.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create Year object
        Year ym = Year.of(2019);

        // apply query method of Year class
        String value
 = ym.query(TemporalQueries
.precision())
.toString();

        // print the result
        System.out.println("Precision value"
+" for Year is " 
+ value);
    }
}
```

**Output:**

```
Precision value for Year is Years

```

**程序 2:** 显示如果查询没有找到所需的对象，则返回空值。

```
// Java program to demonstrate
// Year.query() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create Year object
        Year ym = Year.of(2019);

        // apply query method of Year class
        // print the result
        System.out.println("offset value for Year is " 
+ ym.query(
TemporalQueries.offset()));
    }
}
```

**Output:**

```
offset value for Year is null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # query(Java . time . temporal query)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#query(java.time.temporal.TemporalQuery))
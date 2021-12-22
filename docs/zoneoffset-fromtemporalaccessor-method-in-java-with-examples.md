# Java 中的 zone offset from(time alaccessor)方法，示例

> 原文:[https://www . geeksforgeeks . org/zone offset-from emporalacessor-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-fromtemporalaccessor-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **from(临时进程)**方法用于使用作为参数传递的临时进程中的偏移量来获取 ZoneOffset 的实例。该方法以临时处理器的形式将临时处理器作为参数，并将其转换为区域偏移量。

**语法:**

```
public static ZoneOffset
  from(TemporalAccessor temporalAccessor)

```

**参数:**该方法接受一个参数**临时进程**，该参数是要转换为区域偏移实例的临时进程。

**返回值:**这个方法返回一个从指定的临时处理器解析的**区域偏移实例**。

**异常:**如果临时处理器无效，该方法抛出**日期时间异常**。

以下示例说明了 ZoneOffset.from()方法:

**例 1:**

```
// Java code to illustrate from() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the temporalAccessor
        TemporalAccessor temporalAccessor
            = ZonedDateTime.now();

        // ZoneOffset using from() method
        ZoneOffset zoneOffset
            = ZoneOffset.from(temporalAccessor);

        System.out.println(zoneOffset);
    }
}
```

**输出:**

```
Z

```

**示例 2:** 演示日期时间异常

```
// Java code to illustrate from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        try {
            // ZoneOffset using from() method
            ZoneOffset zoneOffset
                = ZoneOffset.from(LocalDate.now());
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.time.DateTimeException:
 Unable to obtain ZoneOffset from TemporalAccessor:
 2018-12-11 of type java.time.LocalDate

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#from-java.time.temporal.TemporalAccessor-)
# Java 中的年月加(长，单位)方法，示例

> 原文:[https://www . geesforgeks . org/year month-pluslongunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-pluslongunit-method-in-java-with-examples/)

**YearMonth** 类的 **plus(long，unit)** 方法，用于将指定数量的 TemporalUnit 添加到此 Year-month 对象后返回此 Year-month 的副本。如果指定的单位不能添加到年-月，将引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public YearMonth plus(long amountToadd, TemporalUnit unit)
```

**参数:**该方法接受两个参数:

*   **金额增加**:此参数代表要添加到结果中的单位金额。
*   **单位**此参数代表要添加的量的单位。

**返回值:**该方法根据该年-月返回一个年-月，并加上指定的金额。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行加法运算，则会引发此异常。
*   **unsupportedtemporaltypexception–**如果不支持该单元，将引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了加号(长，单位)方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// YearMonth.plus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // apply plus(long, unit) method
        // adding 15 Years
        YearMonth value
            = thisYearMonth.plus(15, ChronoUnit.YEARS);

        // print result
        System.out.println("After addition YearMonth: "
                           + value);
    }
}
```

**Output:** 

```java
YearMonth :2017-08
After addition YearMonth: 2032-08
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// YearMonth.plus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2019, 12);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // apply plus(long, unit) method
        // adding 30 Months
        YearMonth value
            = thisYearMonth.plus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("After addition YearMonth: "
                           + value);
    }
}
```

**Output:** 

```java
YearMonth :2019-12
After addition YearMonth: 2022-06
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # plus(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#plus(long, java.time.temporal.TemporalUnit))
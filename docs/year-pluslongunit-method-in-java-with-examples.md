# Java 中的年加(长，单位)方法，示例

> 原文:[https://www . geesforgeks . org/year-pluslongunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-pluslongunit-method-in-java-with-examples/)

**Year** 类的**加(长，单位)**方法是将指定数量的单位加入到 Year 对象后，返回一份今年的副本。如果指定的单位不能添加到此年份对象，将引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public Year plus(long amountToadd, TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **金额增加**:此参数代表要添加到结果中的单位金额。
*   **单位**:此参数代表要添加的金额的单位。

**返回值:**此方法返回一个基于本年度的*年度*，并加上指定的金额。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行加法运算，则会引发此异常。
*   **unsupportedtemporaltypexception–**如果不支持该单元，将引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了加号(长，单位)方法:

**程序 1:**

```java
// Java program to demonstrate
// Year.plus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2019);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply plus(long, unit) method
        // adding 30 years
        Year value
            = year.plus(30, ChronoUnit.YEARS);

        // print result
        System.out.println("After addition year: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
After addition year: 2049

```

**程序 2:**

```java
// Java program to demonstrate
// Year.plus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2022);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply plus(long, unit) method
        // adding 50 years
        Year value
            = year.plus(50, ChronoUnit.YEARS);

        // print result
        System.out.println("After addition year: "
                           + value);
    }
}
```

**Output:**

```java
Year :2022
After addition year: 2072

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # plus(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#plus(long, java.time.temporal.TemporalUnit))
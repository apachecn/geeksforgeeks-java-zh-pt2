# Java 中的 Year atDay()方法

> 原文:[https://www.geeksforgeeks.org/year-atday-method-in-java/](https://www.geeksforgeeks.org/year-atday-method-in-java/)

Java 中 Year 类的 atDay()方法将当前年份与作为参数传递给它的一年中的某一天相结合，以创建一个 LocalDate。

**语法**:

```java
public LocalDate atDay(int dayOfYear)
```

**参数**:此方法接受单个参数 dayOfYear。这是一年中的一天。它可以取 1 到 365-366 之间的值。

**返回值**:返回当前年份形成的本地日期和作为参数传递给函数的年份日期。

**异常**:此方法抛出 **DateTimeException** ，如果参数中传递的年月日无效，即小于等于零、大于等于 366 且当前年份不是闰年。

下面的程序说明了 Java 中的 atDay()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the atDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates a Year object
        Year thisYear = Year.of(2017);

        // Creates a local date with this
        // Year object and day passed to it
        LocalDate date = thisYear.atDay(31);

        System.out.println(date);
    }
}
```

**Output:** 

```java
2017-01-31
```

**程序 2** :说明异常。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the atDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates a Year object
        Year thisYear = Year.of(2017);

        // Creates a local date with this
        // Year object and day passed to it
        try {
            LocalDate date = thisYear.atDay(367);
            System.out.println(date);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:** 

```java
java.time.DateTimeException: Invalid value for DayOfYear (valid values 1 - 365/366): 367
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # atDay-int-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#atDay-int-)
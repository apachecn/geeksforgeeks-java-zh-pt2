# Java 中的 YearMonth atDay()方法

> 原文:[https://www . geesforgeks . org/year month-at day-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-atday-method-in-java/)

Java 中 YearMonth 类的 atDay()方法将当前的年-月和作为参数传递给它的月-日结合起来，创建一个 LocalDate。

**语法**:

```java
public LocalDate atDay(int dayOfMonth)
```

**参数**:该方法在日接受单个参数*。这是每月的某一天。它可以取 1 到 31 之间的值。*

**返回值**:返回当前年月日作为参数传递给函数形成的本地日期。

**异常**:如果参数中传递的月日无效，该方法抛出**日期时间异常**。

下面的程序用 Java 说明了 YearMonth 的 atDay()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the atDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Creates a local date with this
        // YearMonth object and day passed to it
        LocalDate date = thisYearMonth.atDay(31);

        System.out.println(date);
    }
}
```

**Output:** 

```java
2017-08-31
```

**程序 2** :说明异常。下面的程序抛出一个异常，因为 9 月是 30 天而不是 31 天。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the atDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 9);

        try {
            // Creates a local date with this
            // YearMonth object and day passed to it
            LocalDate date = thisYearMonth.atDay(31);

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
java.time.DateTimeException: Invalid date 'SEPTEMBER 31'
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # atDay-int-](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#atDay-int-)
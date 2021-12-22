# Java 中的 YearMonth getMonth()方法

> 原文:[https://www . geesforgeks . org/year month-get month-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-getmonth-method-in-java/)

Java 中 YearMonth 类的 getMonth()方法用于从使用它的 YearMonth 实例中获取月份字段。它将月字段作为月实例返回。

**语法**:

```java
public Month getMonth()

```

**参数**:该方法不接受任何参数。

**返回值**:返回该年月实例的月字段。它不返回值，而是返回一个月实例。

下面的程序说明了 Java 中 YearMonth 的 getMonth()方法:
**程序 1** :

```java
// Program to illustrate the getMonth() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Get the month field
        System.out.println(thisYearMonth.getMonth());
    }
}
```

**Output:**

```java
AUGUST

```

**程序 2** :

```java
// Program to illustrate the getMonth() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2018, 5);

        // Get the month field
        System.out.println(thisYearMonth.getMonth());
    }
}
```

**Output:**

```java
MAY

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # getMonth–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#getMonth--)
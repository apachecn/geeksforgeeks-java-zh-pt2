# Java 中的年月长月方法()

> 原文:[https://www . geesforgeks . org/year month-length of month-in-method-Java/](https://www.geeksforgeeks.org/yearmonth-lengthofmonth-method-in-java/)

Java 中 **YearMonth 类的 **lengthOfMonth()** 方法，用于以天数的形式返回本年度月对象值的月长。月长的值在 1 到 31 的范围内。这种方法也照顾闰年。**

**语法** :

```java
public int lengthOfMonth()

```

**参数**:该方法不接受任何参数。

**返回值**:返回一个以天数表示月长的**整数值**。

下面的程序说明了 Java 中的 lengthOfMonth()方法:

**程序 1** :

```java
// Program to illustrate the lengthOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(2016, 2);

        // Print the length of month in Number
        // of days, 29 in this case as 2016 is
        // a Leap Year
        System.out.println(yearMonth.lengthOfMonth());
    }
}
```

**输出:**

```java
29

```

**程序二** :

```java
// Program to illustrate the lengthOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(1990, 2);

        // Print the length of month in Number
        // of days, 28 in this case as 1990 is
        // not a Leap Year
        System.out.println(yearMonth.lengthOfMonth());
    }
}
```

**输出:**

```java
28

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # length of month–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#lengthOfMonth--)
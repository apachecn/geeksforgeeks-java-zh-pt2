# Java 中的年()方法，示例

> 原文:[https://www . geesforgeks . org/Java 方法年-带示例/](https://www.geeksforgeeks.org/year-of-method-in-java-with-examples/)

Java 中 Year 类的 of()方法用于返回 Year 实例。它根据[预定义的 ISO 日历系统](https://en.wikipedia.org/wiki/Proleptic_Gregorian_calendar)接受一年，并返回一个带有指定 isoyear 的 Year 实例。

**语法** :

```
public static Year of(int isoYear)

```

**参数**:根据序言 ISO 日历系统，接受单个整数值*等年*作为唯一参数。

**返回值**:返回一个年份的实例。

**异常**:如果根据预定义的国际标准化组织日历系统，作为参数传递的年份被发现无效，它将引发日期时间异常。

下面的程序说明了 Java 中 Year 的 length()方法:

**程序 1** :

```
// Program to illustrate the of() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a valid Year object
        // using of() method
        Year thisYear = Year.of(2018);

        // Print the year object
        System.out.println(thisYear);
    }
}
```

**输出:**

```
2018

```

**程序二** :

```
// Program to illustrate the of() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a valid Year object
        // using of() method
        Year thisYear = Year.of(1997);

        // Print the year object
        System.out.println(thisYear);
    }
}
```

**输出:**

```
1997

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # of-int-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#of-int-)
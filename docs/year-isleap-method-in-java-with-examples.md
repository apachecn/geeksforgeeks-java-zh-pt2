# Java 中的 Year isLeap()方法，带示例

> 原文:[https://www . geesforgeks . org/year-islap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-isleap-method-in-java-with-examples/)

Java 中 Year 类的 isLeap()方法是用来检查这个 Year 对象是否是闰年，这是根据 proleptic calendar 系统规则来确定的。

一年有 366 天就是**闰年**。

根据无产历系统规则，如果一年能被 4 整除，那么它就是闰年。

*   Not divisible by 100, but divisible by 400.

**语法**:

```java
public boolean isLeap()

```

**参数**:该方法不接受任何参数。

**返回值**:如果这个 Year 对象的值是一个闰年，根据 proleptic 日历系统规则，它返回一个布尔值 True，否则返回 False。

下面的程序说明了 Java 中的年度方法:

**程序 1** :

```java
// Program to illustrate the isLeap() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        Year firstYear = Year.of(2016);

        // Check if this year object's value is
        // a leap year or not
        System.out.println(firstYear.isLeap());
    }
}
```

**输出:**

```java
true

```

**程序二** :

```java
// Program to illustrate the isLeap() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        Year firstYear = Year.of(1990);

        // Check if this year object's value is
        // a leap year or not
        System.out.println(firstYear.isLeap());
    }
}
```

**输出:**

```java
false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # isLeap–](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#isLeap--)
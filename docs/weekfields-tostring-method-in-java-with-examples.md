# Java 中 WeekFields toString()方法，带示例

> 原文:[https://www . geesforgeks . org/weekfield-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-tostring-method-in-java-with-examples/)

**周字段类**的 **toString()** 方法用于返回该周字段对象的字符串表示。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个 WeekFields 的字符串表示。

下面的程序说明了 WeekFields.toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// WeekFields.toString() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // apply toString()
        String toString = weekFields.toString();

        // print results
        System.out.println("String representation :"
                           + toString);
    }
}
```

**Output:**

```java
String representation :WeekFields[MONDAY, 1]

```

**程序 2:**

```java
// Java program to demonstrate
// WeekFields.toString() method

import java.time.temporal.WeekFields;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        Locale locale = new Locale("EN", "INDIA");

        // create WeekFields
        WeekFields weekFields = WeekFields.of(locale);

        // apply toString()
        String toString = weekFields.toString();

        // print results
        System.out.println("String representation :"
                           + toString);
    }
}
```

**Output:**

```java
String representation :WeekFields[SUNDAY, 1]

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#toString())
# Java 中 WeekFields hashCode()方法示例

> 原文:[https://www . geesforgeks . org/weekfields-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-hashcode-method-in-java-with-examples/)

**周字段类**的 **hashCode()** 方法用于返回该周字段的哈希代码。它返回一个整数值，该整数值是 ValueRange 实例的 hashCode 值。

**语法:**

```
public int hashCode()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个整数值，即 hashCode 值。

下面的程序说明了 WeekFields.hashCode()方法:
**程序 1:**

```
// Java program to demonstrate
// WeekFields.hashCode() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // apply hashCode()
        int hashCode = weekFields.hashCode();

        // print results
        System.out.println("Hash Code:"
                           + hashCode);
    }
}
```

**Output:**

```
Hash Code:1

```

**程序 2:**

```
// Java program to demonstrate
// WeekFields.hashCode() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        Locale locale = new Locale("EN", "US");

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(locale);

        // apply hashCode()
        int hashCode = weekFields.hashCode();

        // print results
        System.out.println("Hash Code:"
                           + hashCode);
    }
}
```

**Output:**

```
Hash Code:43

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#hashCode())
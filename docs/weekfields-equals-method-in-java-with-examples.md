# Java 中 WeekFields 等于()方法，示例

> 原文:[https://www . geesforgeks . org/weekfield-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-equals-method-in-java-with-examples/)

**周字段类**的**等于()**方法用于比较该周字段是否等于作为参数传递的指定对象。比较基于规则的整个状态，即一周的第一天和最少的几天。

**语法:**

```java
public boolean equals(Object object)

```

**参数:**该方法接受作为其他规则比较对象，空返回假。

**返回值:**如果等于指定的规则，则该方法返回真。

下面的程序说明了 WeekFields.equals()方法:
**程序 1:**

```java
// Java program to demonstrate
// WeekFields.equals() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);
        WeekFields otherWeekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // apply equals()
        boolean bothAreEquals
            = weekFields.equals(otherWeekFields);

        // print results
        System.out.println("Equals: "
                           + bothAreEquals);
    }
}
```

**Output:**

```java
Equals: true

```

**程序 2:**

```java
// Java program to demonstrate
// WeekFields.equals() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);
        WeekFields otherWeekFields
            = WeekFields.of(DayOfWeek.SUNDAY, 3);

        // apply equals()
        boolean bothAreEquals
            = weekFields.equals(otherWeekFields);

        // print results
        System.out.println("Equals: "
                           + bothAreEquals);
    }
}
```

**Output:**

```java
Equals: false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#equals())
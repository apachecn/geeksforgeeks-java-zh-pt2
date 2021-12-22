# Java 中 Days()方法的周期，示例

> 原文:[https://www . geesforgeks . org/period-of days-in-Java-method-with-examples/](https://www.geeksforgeeks.org/period-ofdays-method-in-java-with-examples/)

**周期类**的**天数()**方法用于从给定的天数中获取一个周期作为参数。该参数以整数的形式接受。此方法返回给定天数的周期。

**语法:**

```java
public static Period ofDays(int numberOfDays)
```

**参数:**该方法接受单个参数**天数**，即要解析成 Period 对象的天数。

**返回:**该函数返回**周期**，它是用给定天数解析的周期对象。

以下是 Period.ofDays()方法的实现:

**例 1:**

```java
// Java code to demonstrate ofDays() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Days
        int numberOfDays = 5;

        // Parse the numberOfDays into Period
        // using ofDays() method
        Period p = Period.ofDays(numberOfDays);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```java
0 Years
0 Months
5 Days

```

**例 2:**

```java
// Java code to demonstrate ofDays() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Days
        int numberOfDays = -5;

        // Parse the numberOfDays into Period
        // using ofDays() method
        Period p = Period.ofDays(numberOfDays);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```java
0 Years
0 Months
-5 Days

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # ofDays-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#ofDays-int-)
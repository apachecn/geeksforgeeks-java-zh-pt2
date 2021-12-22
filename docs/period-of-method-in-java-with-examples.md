# Java 中()方法的周期，示例

> 原文:[https://www . geeksforgeeks . org/Java 方法时期示例/](https://www.geeksforgeeks.org/period-of-method-in-java-with-examples/)

**周期类**的()方法的**用于从给定的年数、月数和天数中获取周期作为参数。这些参数以整数的形式被接受。此方法返回给定年数、月数和天数的期间。**

**语法:**

```java
public static Period of(
        int numberOfYears, 
        int numberOfMonths,
        int numberOfDays)
```

**参数:**该方法接受以下参数:

*   **Years** : Used to indicate the years that may be negative.
*   **Months** : Indicates the number of months that may be negative.
*   **Days** : Indicates the number of days that may be negative.

**返回:**该函数返回**期间**，该期间是用给定的年、月和日解析的期间对象。

以下是()方法的实现。

**例 1:**

```java
// Java code to demonstrate of() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Years
        int numberOfYears = 1;

        // Get the number of Months
        int numberOfMonths = 5;

        // Get the number of Days
        int numberOfDays = 21;

        // Parse the given amounts into Period
        // using of() method
        Period p
            = Period.of(numberOfYears,
                        numberOfMonths,
                        numberOfDays);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```java
1 Years
5 Months
21 Days

```

**例 2:**

```java
// Java code to demonstrate of() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Years
        int numberOfYears = -2;

        // Get the number of Months
        int numberOfMonths = 10;

        // Get the number of Days
        int numberOfDays = -11;

        // Parse the given amounts into Period
        // using of() method
        Period p
            = Period.of(numberOfYears,
                        numberOfMonths,
                        numberOfDays);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```java
-2 Years
10 Months
-11 Days

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # of-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#of-int-int-int-)
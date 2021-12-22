# Java 中带月()方法的周期，示例

> 原文:[https://www . geesforgeks . org/period-with months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-withmonths-method-in-java-with-examples/)

**期间类**的 **withMonths()** 方法用于获取指定月数的期间。这个月数作为整数值作为参数传递。

**语法:**

```java
public Period withMonths(int numberOfMonths)
```

**参数:**此方法接受一个参数**月数**，即在此期间要更改的月数。

**返回:**该函数返回一个以月数为参数的**周期**。

下面是 Period.withMonths()方法的实现:

**例 1:**

```java
// Java code to demonstrate withMonths() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be withMonthsd
        String period = "P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the number of months
        int numberOfMonths = 5;

        // Change the numberOfMonths of this Period
        // using withMonths() method
        System.out.println("New Period: "
                           + p.withMonths(numberOfMonths));
    }
}
```

**输出:**

```java
Period: P1Y2M21D
New Period: P1Y5M21D

```

**例 2:**

```java
// Java code to demonstrate withMonths() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be withMonthsd
        String period = "-P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the number of months
        int numberOfMonths = -5;

        // Change the numberOfMonths of this Period
        // using withMonths() method
        System.out.println("New Period: "
                           + p.withMonths(numberOfMonths));
    }
}
```

**输出:**

```java
Period: P-1Y-2M-21D
New Period: P-1Y-5M-21D

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # with months-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#withMonths-int-)
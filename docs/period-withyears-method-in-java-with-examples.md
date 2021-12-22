# Java 中带 Years()方法的句点，带示例

> 原文:[https://www . geesforgeks . org/period-with years-in-Java-method-with-examples/](https://www.geeksforgeeks.org/period-withyears-method-in-java-with-examples/)

**周期类**的 **withYears()** 方法用于获取指定年数的周期。这个年数作为整数值作为参数传递。

**语法:**

```
public Period withYears(int numberOfYears)
```

**参数:**此方法接受一个参数**年数**，即在此期间要改变的年数。

**返回:**该函数返回一个以年数为参数的**周期**。

下面是 Period.withYears()方法的实现:

**例 1:**

```
// Java code to demonstrate withYears() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be withYearsd
        String period = "P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the number of years
        int numberOfYears = 5;

        // Change the numberOfYears of this Period
        // using withYears() method
        System.out.println("New Period: "
                           + p.withYears(numberOfYears));
    }
}
```

**输出:**

```
Period: P1Y2M21D
New Period: P5Y2M21D

```

**例 2:**

```
// Java code to demonstrate withYears() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be withYearsd
        String period = "-P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the number of years
        int numberOfYears = -5;

        // Change the numberOfYears of this Period
        // using withYears() method
        System.out.println("New Period: "
                           + p.withYears(numberOfYears));
    }
}
```

**输出:**

```
Period: P-1Y-2M-21D
New Period: P-5Y-2M-21D

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # with years-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#withYears-int-)
# Java 中带 Days()方法的句点，带示例

> 原文:[https://www . geesforgeks . org/period-with days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-withdays-method-in-java-with-examples/)

**期间类**的**带天数()**方法用于获取指定天数的期间。这个天数作为整数值作为参数传递。

**语法:**

```
public Period withDays(int numberOfDays)
```

**参数:**此方法接受一个参数**天数**，即在此期间要更改的天数。

**返回:**该函数返回一个以天数为参数的**周期**。

以下是 Period.withDays()方法的实现:

**例 1:**

```
// Java code to demonstrate withDays() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be withDaysd
        String period = "P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the number of days
        int numberOfDays = 5;

        // Change the numberOfDays of this Period
        // using withDays() method
        System.out.println("New Period: "
                           + p.withDays(numberOfDays));
    }
}
```

**输出:**

```
Period: P1Y2M21D
New Period: P1Y2M5D

```

**例 2:**

```
// Java code to demonstrate withDays() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be withDaysd
        String period = "-P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the number of days
        int numberOfDays = -5;

        // Change the numberOfDays of this Period
        // using withDays() method
        System.out.println("New Period: "
                           + p.withDays(numberOfDays));
    }
}
```

**输出:**

```
Period: P-1Y-2M-21D
New Period: P-1Y-2M-5D

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # with days-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#withDays-int-)
# Java 中的 Period toTotalMonths()方法，带示例

> 原文:[https://www . geeksforgeeks . org/period-tototal months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-tototalmonths-method-in-java-with-examples/)

**期间类**的**至总月数()**方法用于获取给定期间的总月数。它返回一个描述相同内容的长值。

**语法:**

```java
public long toTotalMonths()
```

**参数:**该方法不接受任何参数。

**返回:**该函数返回**长值**，即该期间的总月数。

下面是 Period.toTotalMonths()方法的实现:

**例 1:**

```java
// Java code to demonstrate toTotalMonths() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be toTotalMonthsd
        String period = "P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the total number of months
        // using toTotalMonths() method
        System.out.println("Total number of Months"
                           + " in this Period: "
                           + p.toTotalMonths());
    }
}
```

**输出:**

```java
Period: P1Y2M21D
Total number of Months in this Period: 14

```

**例 2:**

```java
// Java code to demonstrate toTotalMonths() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be toTotalMonthsd
        String period = "-P1Y2M21D";

        // Parse the String into Period
        Period p = Period.parse(period);

        System.out.println("Period: " + p);

        // Get the total number of months
        // using toTotalMonths() method
        System.out.println("Total number of Months"
                           + " in this Period: "
                           + p.toTotalMonths());
    }
}
```

**输出:**

```java
Period: P-1Y-2M-21D
Total number of Months in this Period: -14

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # to total months–](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#toTotalMonths--)
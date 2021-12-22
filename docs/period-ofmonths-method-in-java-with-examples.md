# 月期间()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/period-of-months-in-Java-method-with-examples/](https://www.geeksforgeeks.org/period-ofmonths-method-in-java-with-examples/)

**周期类**的**月()**方法是从给定的月数中获取一个周期作为参数。该参数以整数的形式接受。此方法返回给定月数的周期。

**语法:**

```java
public static Period ofMonths(int numberOfMonths)
```

**参数:**此方法接受单个参数**月数**，即要解析为 Period 对象的月数。

**返回:**该函数返回**期间**，该期间是用给定的月数解析的期间对象。

下面是 Period.ofMonths()方法的实现:

**例 1:**

```java
// Java code to demonstrate ofMonths() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Months
        int numberOfMonths = 5;

        // Parse the numberOfMonths into Period
        // using ofMonths() method
        Period p = Period.ofMonths(numberOfMonths);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```java
0 Years
5 Months
0 Days

```

**例 2:**

```java
// Java code to demonstrate ofMonths() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Months
        int numberOfMonths = -5;

        // Parse the numberOfMonths into Period
        // using ofMonths() method
        Period p = Period.ofMonths(numberOfMonths);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```java
0 Years
-5 Months
0 Days

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # of months-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#ofMonths-int-)
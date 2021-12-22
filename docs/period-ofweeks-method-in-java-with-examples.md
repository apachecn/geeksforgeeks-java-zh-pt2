# Java 中的 Period ofWeeks()方法，示例

> 原文:[https://www . geesforgeks . org/period-of weeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-ofweeks-method-in-java-with-examples/)

**周期类**的**方法用于从给定的周数中获取一个周期作为参数。该参数以整数的形式接受。此方法返回给定周数的周期。**

**语法:**

```
public static Period ofWeeks(int numberOfWeeks)
```

**参数:**该方法接受单个参数 **numberOfWeeks** ，即要解析为 Period 对象的周数。

**返回:**该函数返回**周期**，这是用给定的周数解析的周期对象。

下面是 Period.ofWeeks()方法的实现:

**例 1:**

```
// Java code to demonstrate ofWeeks() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Weeks
        int numberOfWeeks = 5;

        // Parse the numberOfWeeks into Period
        // using ofWeeks() method
        Period p = Period.ofWeeks(numberOfWeeks);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```
0 Years
0 Months
35 Days

```

**例 2:**

```
// Java code to demonstrate ofWeeks() method

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the number of Weeks
        int numberOfWeeks = -5;

        // Parse the numberOfWeeks into Period
        // using ofWeeks() method
        Period p = Period.ofWeeks(numberOfWeeks);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```
0 Years
0 Months
-35 Days

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # ofWeeks-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#ofWeeks-int-)
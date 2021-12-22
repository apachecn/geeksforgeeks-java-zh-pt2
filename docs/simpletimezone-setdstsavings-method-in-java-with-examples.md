# Java 中的 SimpleTimeZone setDSTSavings()方法，示例

> 原文:[https://www . geeksforgeeks . org/simple time zone-setdstssaves-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-setdstsavings-method-in-java-with-examples/)

**SimpleTimeZone 类**的**setdstsings()**方法用于设置夏令时时钟提前的时间量。计算在毫秒内完成。

**语法:**

```java
public void setDSTSavings(int millisSavedDuringDST)

```

**参数:**该函数接受单个参数**毫秒延迟时间**，该参数指定时间相对于标准时间提前的毫秒数。

**返回值:**该方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function SimpleTimeZone.setDSTSavings()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(-28800000,
                                 "US",
                                 Calendar.MAY,
                                 1,
                                 -Calendar.SUNDAY,
                                 7200000,
                                 Calendar.NOVEMBER,
                                 -1,
                                 Calendar.MONDAY,
                                 7000000,
                                 3500000);

        // printing DST value
        System.out.println("Inittally DST saving value is = "
                           + obj.getDSTSavings());

        // setting DST saving time on object obj
        obj.setDSTSavings(6000000);
        System.out.println("DST saving value "
                           + "set to 6000000");

        // printing DST value
        System.out.println("Current DST saving value is = "
                           + obj.getDSTSavings());
    }
}
```

**Output:**

```java
Inittally DST saving value is = 3500000
DST saving value set to 6000000
Current DST saving value is = 6000000

```

**程序 2:**

```java
// program to demonstrate the
// function SimpleTimeZone.setDSTSavings()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(-28800000,
                                 "US",
                                 Calendar.MAY,
                                 1,
                                 -Calendar.MONDAY,
                                 7200000,
                                 Calendar.JULY,
                                 -1,
                                 Calendar.MONDAY,
                                 7000000,
                                 3500000);

        // printing DST value
        System.out.println("Inittally DST saving value is = "
                           + obj.getDSTSavings());

        // setting DST saving time on object obj
        obj.setDSTSavings(4000000);
        System.out.println("DST saving value "
                           + "set to 4000000");

        // printing DST value
        System.out.println("Current DST saving value is = "
                           + obj.getDSTSavings());
    }
}
```

**Output:**

```java
Inittally DST saving value is = 3500000
DST saving value set to 4000000
Current DST saving value is = 4000000

```
# Java 中的 SimpleDateFormat getDateFormatSymbols()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateformat-getdateformatsymbols-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-getdateformatsymbols-method-in-java-with-examples/)

**简单日期格式类**的**获取日期格式符号()**方法用于返回日期和时间格式符号的副本。

**语法:**

```
public DateFormatSymbols getDateFormatSymbols()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回格式符号的副本。

下面的程序说明了简单日期格式的 getDateFormatSymbols()方法的工作原理:

**例 1:**

```
// Java code to illustrate
// getDateFormatSymbols() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
    {

        // Initializing the SDF
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Getting al DateFormatSymbols
        DateFormatSymbols DFSymbol
            = SDFormat.getDateFormatSymbols();

        // Getting the months
        String[] month = DFSymbol.getShortMonths();
        System.out.println("The Months are: ");
        for (int i = 0; i < month.length; i++) {
            System.out.println(month[i] + " ");
        }
    }
}
```

**Output:**

```
The Months are: 
Jan 
Feb 
Mar 
Apr 
May 
Jun 
Jul 
Aug 
Sep 
Oct 
Nov 
Dec  

```

**例 2:**

```
// Java code to illustrate
// getDateFormatSymbols() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
    {

        // Initializing the SDF
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Getting al DateFormatSymbols
        DateFormatSymbols DFSymbol
            = SDFormat.getDateFormatSymbols();

        // Getting the weekdays
        String[] days = DFSymbol.getWeekdays();
        System.out.println("The days of the week are: ");
        for (int i = 0; i < days.length; i++) {
            System.out.println(days[i] + " ");
        }
    }
}
```

**Output:**

```
The days of the week are: 

Sunday 
Monday 
Tuesday 
Wednesday 
Thursday 
Friday 
Saturday 

```
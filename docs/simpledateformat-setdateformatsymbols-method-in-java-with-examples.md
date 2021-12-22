# Java 中的 SimpleDateFormat setDateFormatSymbols()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateformat-setdateformatsymbols-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-setdateformatsymbols-method-in-java-with-examples/)

**简单日期格式类**的**设置日期格式符号()**方法用于设置该日期格式的日期和时间格式符号。

**语法:**

```
public void setDateFormatSymbols(DateFormatSymbols *newFormatSymbols*)
```

**参数:**该方法取一个参数**新格式符号**，指的是该日期格式要设置成的新格式符号。

**返回值:**该方法返回 void 类型。

以下程序说明了简单日期格式的 setDateFormatSymbols()方法:
**示例 1:**

```
// Java code to illustrate
// DateFormatSymbols() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException, ParseException
    {
        // Initializing SimpleDateFormat
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Setting the DateFormatSymbols
        DateFormatSymbols DFSymbols
            = new DateFormatSymbols(
                new Locale("en",
                           "US"));

        // Illustrating the set method
        SDFormat.setDateFormatSymbols(DFSymbols);

        // Displaying the formats
        Date date = new Date();
        String str_Date1 = SDFormat.format(date);
        System.out.println("The SimpleDateFormat: "
                           + (str_Date1));

        // Working of DFS
        String[] the_days
            = DFSymbols.getShortWeekdays();
        int i, j = 1;
        for (i = 1; i < the_days.length; i++) {
            System.out.print("Day" + j++ + " : "
                             + the_days[i] + "\n");
        }
    }
}
```

**Output:**

```
The SimpleDateFormat: 1/30/19 10:27 AM
Day1 : Sun
Day2 : Mon
Day3 : Tue
Day4 : Wed
Day5 : Thu
Day6 : Fri
Day7 : Sat

```

**例 2:**

```
// Java code to illustrate
// DateFormatSymbols() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException, ParseException
    {
        // Initializing SimpleDateFormat
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Setting the DateFormatSymbols
        DateFormatSymbols DFSymbols
            = new DateFormatSymbols(
                new Locale("es",
                           "XL"));

        // Illustrating the set method
        SDFormat.setDateFormatSymbols(DFSymbols);

        // Displaying the formats
        Date date = new Date();
        String str_Date1 = SDFormat.format(date);
        System.out.println("The SimpleDateFormat: "
                           + (str_Date1));

        // Working of DFS
        String[] the_days
            = DFSymbols.getShortWeekdays();
        int i, j = 1;
        for (i = 1; i < the_days.length; i++) {
            System.out.print("Day" + j++ + " : "
                             + the_days[i] + "\n");
        }
    }
}
```

**Output:**

```
The SimpleDateFormat: 1/30/19 10:28 AM
Day1 : dom
Day2 : lun
Day3 : mar
Day4 : mi?
Day5 : jue
Day6 : vie
Day7 : s?b

```
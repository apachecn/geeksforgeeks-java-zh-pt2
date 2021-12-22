# Java 中的 SimpleDateFormat set 2 digitiyarstart()方法，示例

> 原文:[https://www . geesforgeks . org/simpledateform-set 2 digitiyarstart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-set2digityearstart-method-in-java-with-examples/)

**简单日期格式类**的**设置 2 位数开始()**方法用于设置 100 年期间 2 位数的年份，并将其解释为从用户特定的日期开始。该方法解析日期并将日期设置在从*起始 _ 日期*到*(起始 _ 日期+ 100)* 年的范围内。
**语法:**

```
public void set2DigitYearStart(Date *starting_Date*)
```

**参数:**该方法取日期类型的一个参数**起始日期**，该参数是指该方法中的起始日期，范围可达(起始日期+ 100)年。
**返回值:**该方法返回一个空类型。
以下程序说明了简单日期格式的 set2DigitYearStart()方法的工作:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate set2DigitYearStart() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {

        SimpleDateFormat dt
            = new SimpleDateFormat("MM/ dd/ yy");

        try {
            Calendar cal = Calendar.getInstance();
            cal.setTime(dt.parse("10/ 27/ 16"));
            System.out.println("The Starting Time: "
                               + cal.getTime());

            // Setting 1916 instead of 2016
            // Using set2DigitYearStart() method
            dt.set2DigitYearStart(
                dt.parse("01/ 01/ 1900"));
            cal.setTime(dt.parse("06/ 12/ 16"));
            System.out.println("The New Time: "
                               + cal.getTime());
        }

        catch (ParseException except) {
            except.printStackTrace();
        }
    }
}
```

**Output:** 

```
The Starting Time: Thu Oct 27 00:00:00 UTC 2016
The New Time: Mon Jun 12 00:00:00 UTC 1916
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate set2DigitYearStart() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {

        SimpleDateFormat dt
            = new SimpleDateFormat("MM/ dd/ yy");

        try {
            Calendar cal = Calendar.getInstance();
            cal.setTime(dt.parse("01/ 28/ 19"));
            System.out.println("The Starting Time: "
                               + cal.getTime());

            // Setting 1916 instead of 2016
            // Using set2DigitYearStart() method
            dt.set2DigitYearStart(
                dt.parse("01/ 01/ 1900"));
            cal.setTime(dt.parse("05/ 12/ 17"));
            System.out.println("The New Time: "
                               + cal.getTime());
        }

        catch (ParseException except) {
            except.printStackTrace();
        }
    }
}
```

**Output:** 

```
The Starting Time: Mon Jan 28 00:00:00 UTC 2019
The New Time: Sat May 12 00:00:00 UTC 1917
```
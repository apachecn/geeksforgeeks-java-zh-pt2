# Java 中的 SimpleDateFormat get2 digitiyarstart()方法，示例

> 原文:[https://www . geesforgeks . org/simpledateform-get2 digitiyarstart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-get2digityearstart-method-in-java-with-examples/)

**SimpleDateFormat 类**的**get2 digitiyarstart()**方法用于返回解析或 set2DigitYearStart()方法中设置的 100 年期间的开始。它返回 100 年期间的开始日期，2 位数的年份被解释为在日期内设置。
**语法:**

```java
public Date get2DigitYearStart()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回被解释为在日期
内设置的 100 年期两位数年份的开始日期。以下程序说明了简单日期格式的 get2DigitYearStart()方法的工作原理:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// get2DigitYearStart() method

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

            // Use of get2DigitYearStart() method
            // to check start year
            cal.setTime(dt.get2DigitYearStart());
            System.out.println("The start Year: "
                               + cal.get(Calendar.YEAR));
        }

        catch (ParseException except) {
            except.printStackTrace();
        }
    }
}
```

**Output:** 

```java
The Starting Time: Mon Jan 28 00:00:00 UTC 2019
The New Time: Sat May 12 00:00:00 UTC 1917
The start Year: 1900
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// get2DigitYearStart() method

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
                dt.parse("01/ 01/ 2000"));
            cal.setTime(dt.parse("05/ 12/ 17"));
            System.out.println("The New Time: "
                               + cal.getTime());

            // Use of get2DigitYearStart() method
            // to check start year
            cal.setTime(dt.get2DigitYearStart());
            System.out.println("The start Year: "
                               + cal.get(Calendar.YEAR));
        }

        catch (ParseException except) {
            except.printStackTrace();
        }
    }
}
```

**Output:** 

```java
The Starting Time: Mon Jan 28 00:00:00 UTC 2019
The New Time: Fri May 12 00:00:00 UTC 2017
The start Year: 2000
```
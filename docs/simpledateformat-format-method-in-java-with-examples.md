# Java 中的 SimpleDateFormat()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateform-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-format-method-in-java-with-examples/)

**简单日期格式类**的**格式()**方法用于将给定日期格式化为日期/时间字符串。基本上，该方法用于将该日期和时间转换为特定格式，例如 mm/dd/yyyy。
**语法:**

```
public final String format(Date date)
```

**参数:**该方法取*日期*对象类型的一个参数**日期**，是指要产生字符串输出的日期。
**返回值:**该方法以 mm/dd/yyyy 的字符串格式返回日期或时间。
下面的程序说明了简单日期格式的格式()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate format() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        SimpleDateFormat SDFormat
            = new SimpleDateFormat("MM/dd/yyyy");

        // Initializing the calendar Object
        Calendar cal = Calendar.getInstance();

        // Displaying the actual date
        System.out.println("The original Date: "
                           + cal.getTime());

        // Using format() method for conversion
        String curr_date
            = SDFormat.format(cal.getTime());
        System.out.println("Formatted Date: "
                           + curr_date);
    }
}
```

**Output:** 

```
The original Date: Tue Jan 29 12:23:40 UTC 2019
Formatted Date: 01/29/2019
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate format() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Initializing the calendar Object
        Calendar cal = Calendar.getInstance();

        // Displaying the actual date
        System.out.println("The original Date: "
                           + cal.getTime());

        // Using format() method for conversion
        String curr_date = SDFormat.format(cal.getTime());
        System.out.println("Formatted Date: "
                           + curr_date);
    }
}
```

**Output:** 

```
The original Date: Tue Jan 29 12:29:32 UTC 2019
Formatted Date: 1/29/19 12:29 PM
```
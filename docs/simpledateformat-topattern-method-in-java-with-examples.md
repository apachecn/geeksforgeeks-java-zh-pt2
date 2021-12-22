# Java 中的 SimpleDateFormat toPattern()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateform-topattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-topattern-method-in-java-with-examples/)

**SimpleDateFormat 类**的 **toPattern()** 方法用于返回日期格式的模式。

**语法:**

```
public String toPattern()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回描述该日期格式的模式字符串。

下面的程序说明了简单日期格式的 toPattern()方法的工作原理:

**例 1:**

## 爪哇

```
// Java code to illustrate toPattern() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        SimpleDateFormat SDformat
            = new SimpleDateFormat();

        // Initializing Calendar object
        Calendar cal = Calendar.getInstance();

        // Getting the Current Date
        String Todaysdate
            = SDformat.format(cal.getTime());

        // Displaying the date
        System.out.println("Current Date: "
                           + Todaysdate);

        // Using toPattern() method
        // to Print the Date Pattern
        System.out.println("The Date Pattern- "
                           + SDformat.toPattern());
    }
}
```

**输出:**

```
Current Date: 1/29/19 6:05 AM
The Date Pattern- M/d/yy h:mm a
```
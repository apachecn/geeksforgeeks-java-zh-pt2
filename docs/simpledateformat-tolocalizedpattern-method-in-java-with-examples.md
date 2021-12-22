# Java 中的 SimpleDateFormat to localizedppatten()方法，带示例

> 原文:[https://www . geeksforgeeks . org/simpledateform-tolocalizedppattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-tolocalizedpattern-method-in-java-with-examples/)

**SimpleDateFormat 类**的**to localizedppattern()**方法用于返回描述该日期格式的本地化模式格式化字符串。换句话说，一个特定的日期被转换成一个本地模式，例如 *M/d/yy h:mm a* 。

**语法:**

```java
public String toLocalizedPattern()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回日期格式化程序的本地化模式字符串。

下面的程序说明了简单日期格式的方法的工作原理:

**例 1:**

```java
// Java code to illustrate
// toLocalizedPattern() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Initializing date Formatter
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Initializing the calender Object
        Calendar cal = Calendar.getInstance();

        // Displaying the date
        System.out.println("Date: "
                           + SDFormat.format(
                                 cal.getTime()));

        // Use of toLocalizedPattern() method
        System.out.println("In localized pattern: "
                           + SDFormat
                                 .toLocalizedPattern());
    }
}
```

**Output:**

```java
Date: 1/29/19 8:02 AM
In localized pattern: M/d/yy h:mm a

```

**例 2:**

```java
// Java code to illustrate
// toLocalizedPattern() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Initializing date Formatter
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Initializing the calender Object
        Calendar cal = Calendar.getInstance();

        // Displaying the date
        System.out.println("Date: "
                           + SDFormat
                                 .format(
                                     cal.getTime()));

        // Use of toLocalizedPattern() method
        System.out.println("In localized pattern: "
                           + SDFormat
                                 .toLocalizedPattern());
    }
}
```

**Output:**

```java
Date: 1/29/19 12:46 PM
In localized pattern: M/d/yy h:mm a

```
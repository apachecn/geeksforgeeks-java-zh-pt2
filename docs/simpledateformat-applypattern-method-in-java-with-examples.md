# Java 中的 SimpleDateFormat applyPattern()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateform-apply pattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-applypattern-method-in-java-with-examples/)

**简单日期格式类**的**应用模式()**方法用于将给定的已定义模式设置为日期格式。它只是将特定的日期和时间转换为用户定义的特定格式，例如，dd/ MM/ yyyy HH:mm Z 或 MM/ dd/ yyyy HH:mm Z.
**语法:**

```java
public void applyPattern(String *pattern*)
```

**参数:**该方法采用*字符串*类型的一个参数**模式**，并引用该日期格式的新日期和时间模式。
**返回值:**该方法返回 void 类型。
下面的程序说明了简单日期格式的 applyPattern()方法的工作:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// applyPattern() method

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

        // Using the below pattern
        String new_pat = "dd/ MM/ yyyy HH:mm Z";

        // Use of applyPattern() method
        SDFormat.applyPattern(new_pat);

        // Displaying Current date and time
        String curr_date
            = SDFormat.format(cal.getTime());

        System.out.println("The Current Date: "
                           + curr_date);

        // Displaying the pattern
        System.out.println("Applied Pattern: "
                           + SDFormat.toPattern());
    }
}
```

**Output:** 

```java
The Current Date: 29/ 01/ 2019 07:22 +0000
Applied Pattern: dd/ MM/ yyyy HH:mm Z
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// applyPattern() method

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

        // Using the below pattern
        String new_pat = "MM/ dd/ yyyy HH:mm Z";

        // Use of applyPattern() method
        SDFormat.applyPattern(new_pat);

        // Displaying Current date and time
        String curr_date
            = SDFormat.format(cal.getTime());
        System.out.println("The Current Date: "
                           + curr_date);

        // Displaying the pattern
        System.out.println("Applied Pattern: "
                           + SDFormat.toPattern());
    }
}
```

**Output:** 

```java
The Current Date: 01/ 29/ 2019 07:22 +0000
Applied Pattern: MM/ dd/ yyyy HH:mm Z
```
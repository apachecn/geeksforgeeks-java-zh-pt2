# Java 中的 SimpleDateFormat applylocalized pattern()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateform-applylocalized pattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-applylocalizedpattern-method-in-java-with-examples/)

**简单日期格式类**的 **applyLocalizedPattern()** 方法用于将本地化的字符串模式应用于该日期格式。这个模式可以由用户设置。

**语法:**

```java
public void applyLocalizedPattern(String *pattern*)
```

**参数:**该方法采用*字符串*类型的一个参数**模式**，并引用要应用的新日期和时间。
**返回值:**该方法返回 void 类型。

下面的程序说明了简单日期格式的 applyLocalizedPattern()方法的工作原理:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// applyLocalizedPattern() method

import java.text.*;
import java.util.Calendar;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Initializing calendar Object
        Calendar cal = Calendar.getInstance();

        // Using the following pattern
        String new_pat = "MM / dd / yy HH:mm Z";

        // Use of applyLocalizedPattern()
        SDFormat.applyLocalizedPattern(new_pat);

        System.out.println("Applying the format: "
                           + SDFormat
                                 .toLocalizedPattern());
    }
}
```

**Output:** 

```java
Applying the format: MM / dd / yy HH:mm Z
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// applyLocalizedPattern() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String args[])
        throws Exception
    {

        // Initializing SDF
        SimpleDateFormat SDFormat
            = new SimpleDateFormat();

        // Applying LocalizedPattern
        SDFormat.applyLocalizedPattern("dd");
        String str = SDFormat.format(new Date());

        // Printing todays date
        System.out.println("Today is: " + str);

        // Applying LocalizedPattern
        SDFormat.applyLocalizedPattern("MMM");
        String str1 = SDFormat.format(new Date());

        // Printing the month
        System.out.println("Month is: " + str1);
    }
}
```

**Output:** 

```java
Today is: 30
Month is: Jan
```
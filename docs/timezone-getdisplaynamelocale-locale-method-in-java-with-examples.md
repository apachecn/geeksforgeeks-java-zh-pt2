# 时区 getDisplayName(区域设置区域设置)方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/time zone-getdisplayname locale-locale-Java 中的方法-示例/](https://www.geeksforgeeks.org/timezone-getdisplaynamelocale-locale-method-in-java-with-examples/)

Java 中 **TimeZone 类**的**getDisplayName(Locale*Locale _ time*)**方法用于获取该时区的特定名称，该名称在用户传递的指定区域中易于被用户理解。该名称适用于演示和显示目的。

**语法:**

```java
public final String getDisplayName(Locale *locale_time*)
```

**参数:**该方法取 *Locale* 对象类型的一个参数 **locale_time** ，指的是要提供显示名称的区域。

**返回值:**该方法返回指定地区时区的**显示名称。**

下面的程序说明了时区的 getDisplayName()方法的工作:
**示例 1:**

```java
// Java code to illustrate getDisplayName()

import java.util.*;

public class TimeZone_Demo {
    public static void main(String args[])
    {

        // Creating a time zone object
        TimeZone timezone
            = TimeZone
                  .getTimeZone(
                      "Asia/India");

        // Creating the locale
        Locale locale
            = new Locale("ENGLISH",
                         "USA");

        // Getting a display name for specified locale
        String display_name
            = timezone
                  .getDisplayName(locale);

        // Display name
        System.out.println("The Display name"
                           + " for the locale is: "
                           + display_name);
    }
}
```

**Output:**

```java
The Display name for the locale is: Greenwich Mean Time

```

**例 2:**

```java
// Java code to illustrate getDisplayName()

import java.util.*;

public class TimeZone_Demo {
    public static void main(String args[])
    {

        // Creating a time zone object
        TimeZone timezone
            = TimeZone
                  .getTimeZone("Australia/Sydney");

        // Creating the locale
        Locale locale = new Locale("ENGLISH",
                                   "Australia");

        // Getting a display name
        // for specified locale
        String display_name
            = timezone
                  .getDisplayName(locale);

        // Display name
        System.out.println("The Display name"
                           + " for the locale is: "
                           + display_name);
    }
}
```

**Output:**

```java
The Display name for the locale is: 
Australian Eastern Standard Time (New South Wales)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getDisplayName(Java . util . locale)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDisplayName(java.util.Locale))
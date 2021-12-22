# 时区 getDisplayName(布尔值，int)Java 中的方法，示例

> 原文:[https://www . geesforgeks . org/time zone-getdisplayname boolean-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getdisplaynameboolean-int-method-in-java-with-examples/)

Java 中时区类的 getDisplayName( *布尔日光，int style* )方法用于获取该时区的特定名称，该名称在用户传递的指定区域设置中易于用户理解。该名称适用于演示和显示目的。

**语法:**

```java
public final String 
    getDisplayName(*boolean daylight, 
                   int style*)
```

**参数:**该方法取两个参数:

*   **日光:**这是布尔类型，指定如果该值为真，则返回日光节约名称否则为假。
*   **风格:**此为 LONG 或 SHORT，指显示风格

**返回值:**该方法返回用户可读的指定区域中时区的显示名称。

下面的程序说明了时区的 getDisplayName()方法的工作:
**示例 1:**

```java
// Java code to illustrate getDisplayName()

import java.util.*;

public class TimeZone_Demo {
    public static void main(String args[])
    {

        // Creating a time zone object
        TimeZone timezone = TimeZone.getDefault();

        // Getting a display name for the specified locale
        String display_name
            = timezone
                  .getDisplayName(true, 0);

        // Display name
        System.out.println("The Display name"
                           + " for the locale is: "
                           + display_name);
    }
}
```

**Output:**

```java
The Display name for the locale is: UTC

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
                  .getTimeZone(
                      "Asia/India");

        // Getting a display name for the specified locale
        String display_name
            = timezone
                  .getDisplayName(true, 1);

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

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getDisplayName(布尔值，%20int)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDisplayName(boolean, %20int))
# Java 中的 ZoneOffset getDisplayName()方法，带示例

> 原文:[https://www . geesforgeks . org/zone offset-getdisplayname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-getdisplayname-method-in-java-with-examples/)

**ZoneOffset** 类的 **getDisplayName()** 方法用于获取适合呈现给用户的区域的文本表示，如“英国时间”或“+02:00”。如果没有找到文本映射，则返回完整的标识。

**语法:**

```java
public String getDisplayName(TextStyle style, Locale locale)

```

**参数:**此方法接受两个参数**样式**和**区域设置**，其中样式表示所需文本的长度，区域设置表示要使用的区域设置。

**返回值:**该方法返回区域的文本值。

下面的程序说明了 getDisplayName()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZoneId.getDisplayName() method

import java.time.*;
import java.time.format.TextStyle;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");

        // get Zone id in style TextStyle.SHORT and
        // Locale = Locale.ENGLISH
        String response
            = zoneOffset.getDisplayName(TextStyle.SHORT,
                                        Locale.ENGLISH);

        // print result
        System.out.println("Display Name: "
                           + response);
    }
}
```

**输出:**

```java
Display Name: +05:30

```

**程序二:**

```java
// Java program to demonstrate
// ZoneId.getDisplayName() method

import java.time.*;
import java.time.format.TextStyle;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");

        // get Zone id in style TextStyle.FULL and
        // Locale = Locale.FRENCH
        String response = zoneOffset.getDisplayName(TextStyle.FULL,
                                                    Locale.FRENCH);

        // print result
        System.out.println("Display Name: "
                           + response);
    }
}
```

**输出:**

```java
Display Name: +05:30

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#getDisplayName(java.time.format.TextStyle, java.util.Locale))
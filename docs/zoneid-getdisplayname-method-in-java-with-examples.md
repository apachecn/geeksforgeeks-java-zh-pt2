# Java 中的 ZoneId getDisplayName()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-getdisplayname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-getdisplayname-method-in-java-with-examples/)

**ZoneId** 类的 **getDisplayName()** 方法用于获取适合呈现给用户的区域的文本表示，如“英国时间”或“+02:00”。如果没有找到文本映射，则返回完整的标识。

**语法:**

```
public String getDisplayName(TextStyle style, Locale locale)

```

**参数:**此方法接受两个参数**样式**和**区域设置**，其中样式表示所需文本的长度，区域设置表示要使用的区域设置。

**返回值:**该方法返回区域的文本值。

下面的程序说明了 getDisplayName()方法:

**程序 1:**

```
// Java program to demonstrate
// ZoneId.getDisplayName() method

import java.time.*;
import java.time.format.TextStyle;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {
        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Europe/Paris");

        // get Zone id in style TextStyle.SHORT and
        // Locale = Locale.ENGLISH
        String response = zoneId.getDisplayName(TextStyle.SHORT, Locale.ENGLISH);

        // print result
        System.out.println("ZoneId:"
                           + response);
    }
}
```

**输出:**

```
ZoneId:CET

```

**程序二:**

```
// Java program to demonstrate
// ZoneId.getDisplayName() method

import java.time.*;
import java.time.format.TextStyle;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Asia/Calcutta");

        // get Zone id in style TextStyle.FULL and
        // Locale = Locale.FRENCH
        String response = zoneId.getDisplayName(TextStyle.FULL,
                                                Locale.FRENCH);

        // print result
        System.out.println("ZoneId: "
                           + response);
    }
}
```

**输出:**

```
ZoneId: Inde

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # getDisplayName(Java . time . format . textstyle，java.util.Locale)](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#getDisplayName(java.time.format.TextStyle, java.util.Locale))
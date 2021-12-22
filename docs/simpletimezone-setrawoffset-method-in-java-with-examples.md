# Java 中的 SimpleTimeZone setRawOffset()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-set raw offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-setrawoffset-method-in-java-with-examples/)

**简单时区类**的**设置时差()**方法用于将基准时区时差设置为格林尼治标准时间。偏移量被添加到世界协调时以获得当地时间。

**语法:**

```
public void setRawOffset(int offsetMillis)

```

**参数:**该函数接受单个参数**偏移量**，该参数指定给定基准时区相对于格林尼治时间的偏移量。

**返回值:**该方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.setRawOffset()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(500, "GMT");

        // printing RawOffset value
        System.out.println("Inittally RawOffset is = "
                           + obj.getRawOffset());

        // setting RawOffset on object obj
        obj.setRawOffset(6000000);
        System.out.println("RawOffset "
                           + "set to 6000000");

        // printing RawOffset value
        System.out.println("Current RawOffset is = "
                           + obj.getRawOffset());
    }
}
```

**Output:**

```
Inittally RawOffset is = 500
RawOffset set to 6000000
Current RawOffset is = 6000000

```

**程序 2:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.setRawOffset()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(800, "GMT");

        // printing RawOffset value
        System.out.println("Inittally RawOffset is = "
                           + obj.getRawOffset());

        // setting RawOffset on object obj
        obj.setRawOffset(8000000);
        System.out.println("RawOffset "
                           + "set to 8000000");

        // printing RawOffset value
        System.out.println("Current RawOffset is = "
                           + obj.getRawOffset());
    }
}
```

**Output:**

```
Inittally RawOffset is = 800
RawOffset set to 8000000
Current RawOffset is = 8000000

```
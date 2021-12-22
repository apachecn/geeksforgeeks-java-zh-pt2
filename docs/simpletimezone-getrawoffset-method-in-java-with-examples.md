# Java 中的 SimpleTimeZone getRawOffset()方法，示例

> 原文:[https://www . geeksforgeeks . org/simple time zone-getraw offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-getrawoffset-method-in-java-with-examples/)

**简单时区类**的 **getRawOffset()** 方法用于获取该时区的格林尼治时间偏移。
**语法:**

```
public int getRawOffset()

```

**参数:**函数不接受任何参数。

**返回值:**以毫秒为单位返回 GMT 偏移值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.getRawOffset()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(580, "INDIA");

        // get raw offset value and print
        System.out.println("Raw Offset is = "
                           + obj.getRawOffset());
    }
}
```

**Output:**

```
Raw Offset is = 580

```

**程序 2:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.getRawOffset()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(640, "INDIA");

        // get raw offset value and print
        System.out.println("Raw Offset is = "
                           + obj.getRawOffset());
    }
}
```

**Output:**

```
Raw Offset is = 640

```
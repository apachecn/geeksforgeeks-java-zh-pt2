# Java 中的 SimpleTimeZone toString()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-tostring-method-in-java-with-examples/)

**SimpleTimeZone 类**的 **toString()** 方法用于获取该时区的字符串表示。

**语法:**

```
public String toString()

```

**参数:**函数不接受任何参数。

**返回值:**该方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.toString()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(700, "US");

        // get string value of time zone
        // and print the result
        System.out.println("String value is = "
                           + obj.toString());
    }
}
```

**Output:**

```
String value is =  java.util.SimpleTimeZone[
    id=US,
    offset=700,
    dstSavings=3600000,
    useDaylight=false,
    startYear=0,
    startMode=0,
    startMonth=0,
    startDay=0,
    startDayOfWeek=0,
    startTime=0,
    startTimeMode=0,
    endMode=0,
    endMonth=0,
    endDay=0,
    endDayOfWeek=0,
    endTime=0,
    endTimeMode=0]

```

**程序 2:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.toString()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(800, "US");

        // get string value of time zone
        // and print the result
        System.out.println("String value is = "
                           + obj.toString());
    }
}
```

**Output:**

```
String value is =  java.util.SimpleTimeZone[
    id=US,
    offset=800,
    dstSavings=3600000,
    useDaylight=false,
    startYear=0,
    startMode=0,
    startMonth=0,
    startDay=0,
    startDayOfWeek=0,
    startTime=0,
    startTimeMode=0,
    endMode=0,
    endMonth=0,
    endDay=0,
    endDayOfWeek=0,
    endTime=0,
    endTimeMode=0]

```
# Java 中的 SimpleTimeZone hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-hashcode-method-in-java-with-examples/)

**简单时区类**的**哈希代码()**方法为简单日期格式对象生成哈希代码。

**语法:**

```java
public int hashCode()

```

**参数:**函数不接受任何参数。

**返回值:**返回该对象的哈希代码。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.hashCode()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(500, "US");

        System.out.println("SimpleTimeZone = "
                           + obj);

        // get hash code value and print
        System.out.println("Hash code is = "
                           + obj.hashCode());
    }
}
```

**Output:**

```java
SimpleTimeZone: java.util.SimpleTimeZone
[ 
 id=US,
 offset=500,
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
 endTimeMode=0
]
Hash code is = 500

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.hashCode()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(500, "IN");

        System.out.println("SimpleTimeZone: "
                           + obj);

        // get hash code value and print
        System.out.println("Hash code is = "
                           + obj.hashCode());
    }
}
```

**Output:**

```java
SimpleTimeZone: java.util.SimpleTimeZone
[ 
 id=IN,
 offset=500,
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
 endTimeMode=0
]
Hash code is = 500

```
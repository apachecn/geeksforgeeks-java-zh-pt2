# Java 中的 SimpleTimeZone clone()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-clone-method-in-java-with-examples/)

**简单时区类**的**克隆()**方法返回这个简单时区实例的克隆。
**语法:**

```java
public Object clone()

```

**参数:**函数不接受任何参数。

**返回值:**返回该实例的克隆。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.clone()
import java.util.SimpleTimeZone;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(520, "India");

        // clone the object and print
        System.out.println("Clone object : "
                           + obj.clone());
    }
}
```

**Output:**

```java
Clone object :  java.util.SimpleTimeZone
[ 
 id=India,
 offset=520,
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

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.clone()
import java.util.SimpleTimeZone;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(120, "India");

        // clone the object and print
        System.out.println("Clone object : "
                           + obj.clone());
    }
}
```

**Output:**

```java
Clone object :  java.util.SimpleTimeZone
[ 
 id=India,
 offset=120,
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

```
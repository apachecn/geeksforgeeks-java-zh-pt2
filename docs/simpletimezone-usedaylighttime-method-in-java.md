# Java 中的 SimpleTimeZone useDaylightTime()方法

> 原文:[https://www . geesforgeks . org/simple time zone-usedaylighttime-method-in-Java/](https://www.geeksforgeeks.org/simpletimezone-usedaylighttime-method-in-java/)

**简单时区类**的 **useDaylightTime()** 方法用于查询该时区是否使用夏令时。

**语法:**

```java
public boolean useDaylightTime()

```

**参数:**函数不接受任何参数。

**返回值:**该方法给出两个返回值中的任意一个:

*   如果该时区使用夏令时，则为“true”
*   如果该时区不使用夏令时，则为“false”

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.useDaylightTime()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(700, "US");

        // checking day light time
        // and printing the result
        System.out.println("Day light time is = "
                           + obj.useDaylightTime());
    }
}
```

**Output:**

```java
Day light time is = false

```

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.useDaylightTime()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(820, "India");

        // checking day light time
        // and printing the result
        System.out.println("Day light time is = "
                           + obj.useDaylightTime());
    }
}
```

**Output:**

```java
Day light time is = false

```
# Java 中的 SimpleTimeZone getDSTSavings()方法，示例

> 原文:[https://www . geeksforgeeks . org/simple time zone-getdstssaves-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-getdstsavings-method-in-java-with-examples/)

**SimpleTimeZone 类**的**getdstsings()**方法返回时钟在夏令时前进的时间量(以毫秒为单位)。
**语法:**

```java
public int getDSTSavings()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回时间相对于标准时间的提前量(以毫秒为单位)。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.date.getDSTSavings()
import java.util.SimpleTimeZone;

public class GFG {

    public static void main(String[] args)
    {

        // creating simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(580, "India");

        // check DST saving and print
        System.out.println("DST saving = "
                           + obj.getDSTSavings());
    }
}
```

**Output:**

```java
DST saving = 0

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.date.getDSTSavings()
import java.util.SimpleTimeZone;

public class GFG {

    public static void main(String[] args)
    {

        // creating simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(580, "US");

        // check DST saving and print
        System.out.println("DST saving = "
                           + obj.getDSTSavings());
    }
}
```

**Output:**

```java
DST saving = 0

```
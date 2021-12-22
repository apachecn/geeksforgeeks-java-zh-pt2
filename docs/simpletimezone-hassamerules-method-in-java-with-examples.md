# Java 中 SimpleTimeZone hasSameRules()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-hassamures-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-hassamerules-method-in-java-with-examples/)

如果此区域与另一个区域具有相同的规则和偏移，则**简单时区类**的**hassamures()**方法返回“真”。

**语法:**

```
public boolean hasSameRules(TimeZone other)

```

**参数:**函数接受单个参数**其他**，这是要比较的时区对象。

**返回值:**如果给定区域是简单时区，并且与该区域具有相同的规则和偏移量，则返回**“真”**。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.hasSameRules()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create first simple time zone object
        SimpleTimeZone obj1
            = new SimpleTimeZone(720, "US");

        // create second simple time zone object
        SimpleTimeZone obj2
            = new SimpleTimeZone(800, "GMT");

        // check rules for both objects and print the result
        System.out.println("Hash same rule = "
                           + obj1.hasSameRules(obj2));
    }
}
```

**Output:**

```
Hash same rule = false

```

**程序 2:**

```
// program to demonstrate the
// function java.util.SimpleTimeZone.hasSameRules()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create first simple time zone object
        SimpleTimeZone obj1
            = new SimpleTimeZone(720, "US");

        // create second simple time zone object
        SimpleTimeZone obj2
            = new SimpleTimeZone(720, "GMT");

        // check rules for both objects and print the result
        System.out.println("Hash same rule = "
                           + obj1.hasSameRules(obj2));
    }
}
```

**Output:**

```
Hash same rule = true

```
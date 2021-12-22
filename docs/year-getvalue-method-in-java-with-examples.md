# Java 中 Year getValue()方法，带示例

> 原文:[https://www . geesforgeks . org/year-getvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-getvalue-method-in-java-with-examples/)

Java 中 Year 类的 getValue()方法用于获取当前 Year 对象的整数值。

**语法** :

```
public int getValue()

```

**参数**:该方法不接受任何参数。

**返回值**:返回一个表示当前年份对象值的整数。

下面的程序说明了 Java 中的 getValue()方法:

**程序 1** :

```
// Program to illustrate the getvalue() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year firstYear = Year.of(1997);

        // Print the value of the current year
        // using getValue() method
        System.out.println(firstYear.getValue());
    }
}
```

**输出:**

```
1997

```

**程序二** :

```
// Program to illustrate the getvalue() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year firstYear = Year.of(2018);

        // Print the value of the current year
        // using getValue() method
        System.out.println(firstYear.getValue());
    }
}
```

**输出:**

```
2018

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # getValue–](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#getValue--)
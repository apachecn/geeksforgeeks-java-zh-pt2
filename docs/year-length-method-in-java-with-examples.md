# Java 中的年长()方法，带示例

> 原文:[https://www . geesforgeks . org/year-length-in-Java-method-in-examples/](https://www.geeksforgeeks.org/year-length-method-in-java-with-examples/)

Java 中 Year 类的 length()方法用于返回以天数表示的今年对象值的长度。年份只能有两种可能的长度，365(非闰年)和 366(闰年)。

**语法**:

```java
public int length()

```

**参数**:该方法不接受任何参数。

**返回值**:返回一个整数值，以天数表示年的长度。

下面的程序说明了 Java 中年份的长度()方法:
**程序 1** :

```java
// Program to illustrate the length() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object
        Year thisYear = Year.of(2016);

        // Print the length of this year in Number
        // of days, 366 in this case as 2016 is
        // a Leap Year
        System.out.println(thisYear.length());
    }
}
```

**Output:**

```java
366

```

**程序 2** :

```java
// Program to illustrate the length() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object
        Year thisYear = Year.of(1990);

        // Print the length of this year in Number
        // of days, 365 in this case as 1990 is not
        // a Leap Year
        System.out.println(thisYear.length());
    }
}
```

**Output:**

```java
365

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # length–](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#length--)
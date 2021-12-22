# Year now()方法用 Java 举例

> 原文:[https://www . geesforgeks . org/year-now-in-Java-method-in-with-examples/](https://www.geeksforgeeks.org/year-now-method-in-java-with-examples/)

Java 中 Year 类的 now()方法用于从默认时区的系统时钟返回当前年份。

**语法** :

```
public static Year now()

or,
public static Year now(Clock clock)

or,
public static Year now(ZoneId zone)

```

**参数**:该方法的参数是可选的，如上语法所示。

**返回值**:如果没有指定参数，则从默认时区的系统时钟返回当前年份，否则使用指定的时钟和时区返回当前年份。它永远不能返回空值

下面的程序用 Java 说明了 Year 的 length()方法:

**程序 1** :

```
// Program to illustrate the now() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object using now() method
        // It will return the current year from the
        // system clock in the default time-zone.
        Year thisYear = Year.now();

        // Print the year object
        System.out.println(thisYear);
    }
}
```

**输出:**

```
2018

```

**程序 2** :如果时钟被指定为 now()方法的参数。在这种情况下，它将使用默认时区，但不使用系统时钟，而是使用默认时区中作为参数传递给它的时钟。

```
// Program to illustrate the now() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object using now() method
        // It will return the current year from the
        // clock specified in the default time-zone.
        Year thisYear = Year.now(Clock.systemUTC());

        // Print the year object
        System.out.println(thisYear);
    }
}
```

**输出:**

```
2018

```

**程序 3** :如果区域被指定为 now()方法的参数。在这种情况下，它将不会使用默认时区，而是使用时区中的系统时钟作为参数。

```
// Program to illustrate the now() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object using now() method
        // It will return the current year from the
        // system-clock in the time-zone specified
        Year thisYear = Year.now(ZoneId.systemDefault());

        // Print the year object
        System.out.println(thisYear);
    }
}
```

**输出:**

```
2018

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # now–](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#now--)
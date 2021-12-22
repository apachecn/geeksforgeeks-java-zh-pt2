# Java 中的 Year toString()方法，带示例

> 原文:[https://www . geesforgeks . org/year-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-tostring-method-in-java-with-examples/)

Java 中 Year 类的 toString()方法用于返回这个 Year 对象的字符串表示形式。

**语法** :

```
public String toString()

```

**参数**:该方法不接受任何参数。

**返回值**:返回这个 Year 对象的字符串表示。

下面的程序说明了 Java 中的 toString()方法:

**程序 1** :

```
// Program to illustrate the toString() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a valid Year object
        Year thisYear = Year.of(2018);

        // Print the string representation
        System.out.println(thisYear.toString());
    }
}
```

**输出:**

```
2018

```

**程序二** :

```
// Program to illustrate the toString() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a valid Year object
        Year thisYear = Year.of(1997);

        // Print the string representation
        System.out.println(thisYear.toString());
    }
}
```

**输出:**

```
1997

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#toString--)
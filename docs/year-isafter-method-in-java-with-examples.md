# Java 中的 Year isAfter()方法，带示例

> 原文:[https://www . geesforgeks . org/year-is after-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-isafter-method-in-java-with-examples/)

Java 中 Year 类的 isaafter()方法用于检查当前 Year 对象是否在指定为此方法参数的 Year 之后。

**语法**:

```java
public boolean isAfter(Year otherYear)

```

**参数**:接受单个参数 *otherYear* ，与当前 Year 对象进行比较。

**返回值**:如果这个 Year 对象的值在作为方法参数指定的 Year 对象的值之后，则返回布尔值 True，否则返回 False。

下面的程序用 Java 说明了年度的 isAfter()方法:
**程序 1** :

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        Year firstYear = Year.of(2018);

        // Create second Year object
        Year secondYear = Year.of(1997);

        // Check if this year object's value is
        // after the specified Year or not
        System.out.println(firstYear.isAfter(secondYear));
    }
}
```

**Output:**

```java
true

```

**程序 2** :

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        Year firstYear = Year.of(1997);

        // Create second Year object
        Year secondYear = Year.of(2018);

        // Check if this year object's value is
        // after the specified Year or not
        System.out.println(firstYear.isAfter(secondYear));
    }
}
```

**Output:**

```java
false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # isaafter-Java . time . year-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#isAfter-java.time.Year-)
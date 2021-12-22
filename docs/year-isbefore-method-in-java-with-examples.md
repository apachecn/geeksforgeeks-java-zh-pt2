# Year 是 Java 中的 Before()方法，带有示例

> 原文:[https://www . geesforgeks . org/year-is before-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-isbefore-method-in-java-with-examples/)

Java 中 Year 类的 isbbefore()方法用于检查当前 Year 对象是否在指定为此方法参数的 Year 之前。

**语法**:

```java
public boolean isBefore(Year otherYear)

```

**参数**:接受单个参数 *otherYear* ，与当前 Year 对象进行比较。

**返回值**:如果这个 Year 对象的值在指定为方法参数的 Year 对象的值之前，则返回布尔值 True，否则返回 False。

以下程序说明了 Java 中的 isBefore()年方法:
**程序 1** :

```java
// Program to illustrate the isBefore() method

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
        // before the specified Year or not
        System.out.println(firstYear.isBefore(secondYear));
    }
}
```

**Output:**

```java
false

```

**程序 2** :

```java
// Program to illustrate the isBefore() method

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
        // before the specified Year or not
        System.out.println(firstYear.isBefore(secondYear));
    }
}
```

**Output:**

```java
true

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # is before-Java . time . year-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#isBefore-java.time.Year-)
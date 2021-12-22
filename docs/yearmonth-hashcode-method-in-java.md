# Java 中的 YearMonth hashCode()方法

> 原文:[https://www . geesforgeks . org/year month-hashcode-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-hashcode-method-in-java/)

Java 中 YearMonth 类的 hashCode()方法用于为使用它的 YearMonth 实例创建合适的哈希代码。

**语法**:

```java
public int hashCode()

```

**参数**:该方法不接受任何参数。

**返回值**:为这个 YearMonth 实例返回一个合适的整数哈希码值。

下面的程序用 Java 说明了年月的 hashCode()方法:
**程序 1** :

```java
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Get the hash code value
        System.out.println(thisYearMonth.hashCode());
    }
}
```

**Output:**

```java
1073743841

```

**程序 2** :

```java
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2018, 5);

        // Get the hash code value
        System.out.println(thisYearMonth.hashCode());
    }
}
```

**Output:**

```java
671090658

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#hashCode--)
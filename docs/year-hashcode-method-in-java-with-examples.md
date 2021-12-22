# Java 中的 Year hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/year-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-hashcode-method-in-java-with-examples/)

Java 中 Year 类的 hashCode()方法用于为当前 Year 对象获取合适的哈希代码。

**语法**:

```
public int hashCode()

```

**参数**:该方法不接受任何参数。

**返回值**:为使用它的年份对象返回一个合适的整数哈希码。它从不返回空值。

下面的程序说明了 Java 中的 hashCode()方法:
**程序 1** :

```
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year firstYear = Year.of(1997);

        // Print the hash code for
        // the current year object
        System.out.println(firstYear.hashCode());
    }
}
```

**Output:**

```
1997

```

**程序 2** :

```
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year firstYear = Year.of(2018);

        // Print the hash code for
        // the current year object
        System.out.println(firstYear.hashCode());
    }
}
```

**Output:**

```
2018

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#hashCode--)
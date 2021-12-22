# Java 中的 Year 等于()方法，示例

> 原文:[https://www . geesforgeks . org/year-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-equals-method-in-java-with-examples/)

Java 中 Year 类的 equals()方法用于检查这个 Year 对象是否等于作为参数传递的另一个 Year 对象。这种比较是基于年份的时间线位置。

**语法**:

```
public boolean equals(Object obj)

```

**参数**:该方法接受单个参数 *obj* 。是 Year 对象指定了我们要与当前年份对象进行比较的年份。

**返回值**:如果发现当前 Year 对象等于作为参数传递给它的 Year 对象，则返回布尔值 True，否则返回 false。

下面的程序用 Java 说明了 Year 的 equals()方法:
**程序 1** :

```
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates first Year object
        Year firstYear = Year.of(2017);

        // Creates second year object
        Year secondYear = Year.of(2018);

        // Checks if the two year objects are
        // equal or not
        System.out.println(firstYear.equals(secondYear));
    }
}
```

**Output:**

```
false

```

**程序 2** :

```
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates first Year object
        Year firstYear = Year.of(2018);

        // Creates second year object
        Year secondYear = Year.of(2018);

        // Checks if the two year objects are
        // equal or not
        System.out.println(firstYear.equals(secondYear));
    }
}
```

**Output:**

```
true

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#equals-java.lang.Object-)
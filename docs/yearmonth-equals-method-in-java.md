# YearMonth 等于()Java 中的方法

> 原文:[https://www . geesforgeks . org/year-month-equals-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-equals-method-in-java/)

Java 中 YearMonth 类的 equals()方法用于比较两个 YearMonth 对象。它将这个 YearMonth 对象与作为参数传递给它的 YearMonth 对象进行比较，并检查两个 YearMonth 实例是否相等。

**语法**:

```
public boolean equals(Object otherYearMonth)

```

**参数**:该方法接受单个参数 *otherYearMonth* ，即该 YearMonth 要与之比较的其他 YearMonth 实例。

**返回值**:如果本年度月等于其他年度月，则返回真，否则返回假。

下面的程序说明了 Java 中的 YearMonth 的 equals()方法:
**程序 1** :

```
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates first YearMonth object
        YearMonth firstYearMonth = YearMonth.of(2017, 8);

        // Creates second YearMonth object
        YearMonth secondYearMonth = YearMonth.of(2016, 11);

        // check if the two YearMonth instances are equal
        System.out.println(firstYearMonth.equals(secondYearMonth));
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
        // Creates first YearMonth object
        YearMonth firstYearMonth = YearMonth.of(2017, 8);

        // Creates second YearMonth object
        YearMonth secondYearMonth = YearMonth.of(2017, 8);

        // check if the two YearMonth instances are equal
        System.out.println(firstYearMonth.equals(secondYearMonth));
    }
}
```

**Output:**

```
true

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#equals-java.lang.Object-)
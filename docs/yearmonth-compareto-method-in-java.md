# Java 中的 YearMonth compareTo()方法

> 原文:[https://www . geesforgeks . org/year month-compare to-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-compareto-method-in-java/)

Java 中 YearMonth 类的 compareTo()方法用于比较两个 YearMonth 对象。它将这个 YearMonth 对象与作为参数传递给它的 YearMonth 对象进行比较。两个年月实例之间的比较首先基于年的值，然后基于月。

**语法**:

```
public int compareTo(YearMonth otherYearMonth)
```

**参数**:该方法接受单个参数 *otherYearMonth* ，即该 YearMonth 要与之比较的其他 YearMonth 实例。

**返回值**:根据比较结果返回积分比较器值:

*   如果今年的月份大于其他年份的月份，则返回 1。
*   它返回-1，表示该年月小于其他年月。
*   它返回 0 表示这个年月等于另一个年月。

下面的程序说明了 Java 中 YearMonth 的 compareTo()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates first YearMonth object
        YearMonth firstYearMonth = YearMonth.of(2017, 8);

        // Creates second YearMonth object
        YearMonth secondYearMonth = YearMonth.of(2016, 11);

        // compare the two YearMonth instances
        System.out.println(firstYearMonth.compareTo(secondYearMonth));
    }
}
```

**Output:** 

```
1
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates first YearMonth object
        YearMonth firstYearMonth = YearMonth.of(2016, 11);

        // Creates second YearMonth object
        YearMonth secondYearMonth = YearMonth.of(2016, 11);

        // compare the two YearMonth instances
        System.out.println(firstYearMonth.compareTo(secondYearMonth));
    }
}
```

**Output:** 

```
0
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # compare to-Java . time . year month-](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#compareTo-java.time.YearMonth-)T4】
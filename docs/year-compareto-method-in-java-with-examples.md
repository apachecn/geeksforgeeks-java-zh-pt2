# Java 中 Year compareTo()方法与示例

> 原文:[https://www . geesforgeks . org/year-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-compareto-method-in-java-with-examples/)

Java 中 Year 类的 compareTo()方法用于比较这个 Year 对象和另一个 Year 对象。年份对象的比较基于年份的值。
**语法** :

```
public int compareTo(Year otherYear)
```

**参数**:该方法接受单个参数 *otherYear* 。是 Year 对象指定了我们要与当前年份对象进行比较的年份。
**返回值**:根据两个年份对象的比较，返回一个积分比较值。
下面的程序说明了 Java 中 year 的 compareTo()方法:
**程序 1** :在这个程序中当前 Year 对象的值小于第二个 Year 对象的值。所以，返回值是-1。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates first Year object
        Year firstYear = Year.of(2017);

        // Creates second year object
        Year secondYear = Year.of(2018);

        // Compare the two years and print the
        // comparator value
        System.out.println(firstYear.compareTo(secondYear));
    }
}
```

**Output:** 

```
-1
```

**程序 2** :在本程序中，当前年份对象的值等于第二个年份对象。因此，返回值为 0。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates first Year object
        Year firstYear = Year.of(2018);

        // Creates second year object
        Year secondYear = Year.of(2018);

        // Compare the two years and print the
        // comparator value
        System.out.println(firstYear.compareTo(secondYear));
    }
}
```

**Output:** 

```
0
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # compare to-Java . time . year-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#compareTo-java.time.Year-)T4】
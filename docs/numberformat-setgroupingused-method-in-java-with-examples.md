# number format setgroungused()方法在 Java 中的示例

> 原文:[https://www . geeksforgeeks . org/number format-set group used-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setgroupingused-method-in-java-with-examples/)

**setGroupingUsed()** 方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，用于设置要使用的分组。

**语法:**

```java
public void setGroupingUsed(boolean val)
```

**参数**:该功能接受一个强制参数**值**，指定要设置的分组。

**返回值**:该函数不返回任何内容，因此返回类型为 void。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        NumberFormat nF
            = NumberFormat.getNumberInstance();

        System.out.println("Grouping set initially as: "
                           + nF.isGroupingUsed());

        // Set grouping
        nF.setGroupingUsed(false);

        // Print the currency
        System.out.println("Grouping set finally as: "
                           + nF.isGroupingUsed());
    }
}
```

**输出:**

```java
Grouping set initially as: true
Grouping set finally as: false

```

**程序二:**

```java
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        NumberFormat nF
            = NumberFormat.getNumberInstance();

        System.out.println("Grouping set initially as: "
                           + nF.isGroupingUsed());

        // Set grouping
        nF.setGroupingUsed(true);

        // Print the currency
        System.out.println("Grouping set finally as: "
                           + nF.isGroupingUsed());
    }
}
```

**输出:**

```java
Grouping set initially as: true
Grouping set finally as: true

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # setgroupenguised(布尔型)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#setGroupingUsed(boolean))
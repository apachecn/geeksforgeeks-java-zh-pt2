# NumberFormat 设置 setMaximumFractionDigits()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/number format-setmaximumfactiondigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setmaximumfractiondigits-method-in-java-with-examples/)

**setmaximumfactiondigits()**方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，它设置一个数字的小数部分允许的最大位数。如果最大值的新值小于最小值分数位数的当前值，则最小值分数位数也将设置为新值。

**语法:**

```java
public void setMaximumFractionDigits(int val)
```

**参数**:该功能接受一个强制参数**值**，该值指定要设置的最大值。

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

        System.out.println("Maximum set initially as: "
                           + nF.getMaximumFractionDigits());

        // Set grouping
        nF.setMaximumFractionDigits(100);

        // Print the final
        System.out.println("Maximum set finally as: "
                           + nF.getMaximumFractionDigits());
    }
}
```

**输出:**

```java
Maximum set initially as: 3
Maximum set finally as: 100

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

        System.out.println("Maximum set initially as: "
                           + nF.getMaximumFractionDigits());

        // Set grouping
        nF.setMaximumFractionDigits(6785);

        // Print the final
        System.out.println("Maximum set finally as: "
                           + nF.getMaximumFractionDigits());
    }
}
```

**输出:**

```java
Maximum set initially as: 3
Maximum set finally as: 6785

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # setmaximumfactiondigits(int)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#setMaximumFractionDigits(int))
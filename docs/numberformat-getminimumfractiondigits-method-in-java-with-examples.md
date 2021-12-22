# number format getMinimumFractionDigits()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/number format-getminimumrocidigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getminimumfractiondigits-method-in-java-with-examples/)

**getMinimumFractionDigits()**方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，返回一个实例的数字的小数部分允许的最小位数。

**语法** :

```
public int getMinimumFractionDigits()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回小数部分允许的最大位数。

下面是上述功能的实现:

**程序 1:**

```
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the Integer instance
        NumberFormat nF
            = NumberFormat
                  .getIntegerInstance();

        // Stores the minimum
        int value
            = nF.getMinimumFractionDigits();

        // Prints the maximum fraction
        System.out.println("The minimum "
                           + "Fraction digits: "
                           + value);
    }
}
```

**输出:**

```
The minimum Fraction digits: 0

```

**程序二:**

```
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the Currency instance
        NumberFormat nF
            = NumberFormat
                  .getCurrencyInstance();

        // Stores the minimum
        int value
            = nF.getMinimumFractionDigits();

        // Prints the minimum
        System.out.println("The minimum "
                           + "Fraction digits: "
                           + value);
    }
}
```

**输出:**

```
The minimum Fraction digits: 2

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getMinimumFractionDigits()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getMinimumFractionDigits())
# Java 中 NumberFormat setMinimumFractionDigits()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-setminimumrocidigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setminimumfractiondigits-method-in-java-with-examples/)

**setMinimumFractionDigits()**方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，它设置一个数字的小数部分允许的最小位数。如果最小值分数位数的新值小于最大值操作位数的当前值，则最大值操作位数也将设置为新值。

**语法:**

```
public void setMinimumFractionDigits(int val)
```

**参数**:该功能接受一个强制参数**值**，该值指定要设置的最小值。

**返回值**:该函数不返回任何内容，因此返回类型为 void。

下面是上述功能的实现:

**程序 1** :

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

        NumberFormat nF
            = NumberFormat.getNumberInstance();

        System.out.println("Minimum set initially as: "
                           + nF.getMinimumFractionDigits());

        // Set grouping
        nF.setMinimumFractionDigits(100);

        // Print the final
        System.out.println("Minimum set finally as: "
                           + nF.getMinimumFractionDigits());
    }
}
```

**输出:**

```
Minimum set initially as: 0
Minimum set finally as: 100

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

        NumberFormat nF
            = NumberFormat.getNumberInstance();

        System.out.println("Minimum set initially as: "
                           + nF.getMinimumFractionDigits());

        // Set grouping
        nF.setMinimumFractionDigits(7998);

        // Print the final
        System.out.println("Minimum set finally as: "
                           + nF.getMinimumFractionDigits());
    }
}
```

**输出:**

```
Minimum set initially as: 0
Minimum set finally as: 7998

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # setMinimumFractionDigits(int)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#setMinimumFractionDigits(int))
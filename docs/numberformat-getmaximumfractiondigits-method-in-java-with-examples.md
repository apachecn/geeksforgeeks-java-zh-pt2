# number format getmaximumfactiondigits()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/number format-getmaximumfactiondigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getmaximumfractiondigits-method-in-java-with-examples/)

**getmaximumfactiondigits()**方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，返回一个实例的数字的小数部分允许的最大位数。

**语法** :

```java
public int getMaximumFractionDigits()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回分数部分允许的最大位数。

下面是上述功能的实现:

**程序 1:**

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

        // Get the Integer instance
        NumberFormat nF
            = NumberFormat
                  .getIntegerInstance();

        // Stores the maximum
        int value
            = nF.getMaximumFractionDigits();

        // Prints the maximum
        System.out.println("The maximum"
                           + " Fraction digits: "
                           + value);
    }
}
```

**输出:**

```java
The maximum Fraction digits: 0

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

        // Get the Currency instance
        NumberFormat nF
            = NumberFormat
                  .getCurrencyInstance();

        // Stores the maximum
        int value
            = nF.getMaximumFractionDigits();

        // Prints the maximum
        System.out.println("The maximum"
                           + " Fraction digits: "
                           + value);
    }
}
```

**输出:**

```java
The maximum Fraction digits: 2

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getmaximumfactiondigits()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getMaximumFractionDigits())
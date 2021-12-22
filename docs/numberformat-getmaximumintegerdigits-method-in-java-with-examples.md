# number format getmaximumitegerdigits()方法在 Java 中用示例

> 原文:[https://www . geeksforgeeks . org/number format-getmaximumintegergits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getmaximumintegerdigits-method-in-java-with-examples/)

**getMaximumIntegerDigits()**方法是一个内置的方法，它返回一个实例的整数部分所允许的最大位数。

**语法** :

```java
public int getMaximumIntegerDigits()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回整数部分允许的最大位数。

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
            = NumberFormat.getIntegerInstance();

        // Stores the maximum
        int value
            = nF.getMaximumIntegerDigits();

        // Prints the maximum integer
        System.out.println("The maximum"
                           + " Integer digits: "
                           + value);
    }
}
```

**输出:**

```java
The maximum Integer digits: 2147483647

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
            = nF.getMaximumIntegerDigits();

        // Prints the minimum
        System.out.println("The maximum"
                           + " integer digits: "
                           + value);
    }
}
```

**输出:**

```java
The maximum integer digits: 2147483647

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getmaximumintegergits()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getMaximumIntegerDigits())
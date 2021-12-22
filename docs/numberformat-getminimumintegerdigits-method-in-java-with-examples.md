# number format getminimumentegerdigits()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/number format-getminimumentegerdigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getminimumintegerdigits-method-in-java-with-examples/)

**getminimumentegerdigits()**方法是一个内置的方法**T3【Java . text . number formatT5】返回一个实例的数字的整数部分允许的最小位数。**

**语法** :

```
public int getMinimumIntegerDigits()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回整数部分允许的最小位数。

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
            = NumberFormat.getIntegerInstance();

        // Stores the minimum
        int value
            = nF.getMinimumIntegerDigits();

        // Prints the minimum integer
        System.out.println("The minimum "
                           + "Integer digits: "
                           + value);
    }
}
```

**输出:**

```
The minimum Integer digits: 1

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
            = nF.getMinimumIntegerDigits();

        // Prints the minimum
        System.out.println("The minimum"
                           + " integer digits: "
                           + value);
    }
}
```

**输出:**

```
The minimum integer digits: 1

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getminimumentegerdigits()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getMinimumIntegerDigits())
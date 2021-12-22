# Java 中的 NumberFormat setCurrency()方法，示例

> 原文:[https://www . geesforgeks . org/number format-set currency-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setcurrency-method-in-java-with-examples/)

**setCurrency()** 方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，用于设置格式化货币值时该数字格式使用的货币。这不会更新数字格式使用的最小或最大分数位数。它会覆盖最初的货币。

**语法:**

```java
public void setCurrency(Currency currency)
```

**参数**:该功能接受一个强制参数**货币**，指定要设置的货币。

**返回值**:该函数不返回任何内容，因此返回类型为 void。

**错误和异常:**该函数抛出两类异常，描述如下:

*   **UnsupportedoperationException** : If the number format class does not implement the currency format.

*   [T0】 NullPointerException 【T1] Thrown if the currency is empty.

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

        // Initially currency
        System.out.println("Initially Currency: "
                           + nF.getCurrency());

        // Currency set to US
        nF.setCurrency(Currency
                           .getInstance(Locale.CANADA));

        // Print the currency
        System.out.println("Currency set as: "
                           + nF.getCurrency());
    }
}
```

**输出:**

```java
Initially Currency: USD
Currency set as: CAD

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
        try {

            NumberFormat nF
                = NumberFormat.getNumberInstance();

            // Initially currency
            System.out.println("Initially Currency: "
                               + nF.getCurrency());

            // Currency set to US
            nF.setCurrency(null);

            // Print the currency
            System.out.println("Currency set as: "
                               + nF.getCurrency());
        }
        catch (Exception e) {
            System.out.println("Exception is: " + e);
        }
    }
}
```

**输出:**

```java
Initially Currency: USD
Exception is: java.lang.NullPointerException

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # setCurrency(Java . util . currency)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#setCurrency(java.util.Currency))
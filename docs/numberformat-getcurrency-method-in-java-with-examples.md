# Java 中的 NumberFormat getCurrency()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getcurrency-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getcurrency-method-in-java-with-examples/)

**getCurrency()** 方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的一个内置方法，返回该货币格式化货币值时使用的货币。如果没有要确定的有效货币，或者如果之前没有设置货币，则可以为空。

**语法** :

```
public Currency getCurrency()
```

**参数**:函数不接受单个参数。

**返回值**:该函数返回格式化货币值时使用的货币。

**错误和异常**:当数字格式类没有实现货币格式时，函数抛出*不支持操作异常*

下面是上述功能的实现:

**程序 1:**

```
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the instance
        NumberFormat nF
            = NumberFormat
                  .getInstance();

        // Stores the values
        String values
            = nF.getCurrency()
                  .getDisplayName();

        // Prints the currency
        System.out.println(values);
    }
}
```

**输出:**

```
US Dollar

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

        // Get the instance
        NumberFormat nF
            = NumberFormat
                  .getNumberInstance();

        // Sets the currency to Canadian Dollar
        nF.setCurrency(
            Currency.getInstance(
                Locale.CANADA));

        // Stores the values
        String values
            = nF.getCurrency()
                  .getDisplayName();

        // Prints the currency
        System.out.println(values);
    }
}
```

**输出:**

```
Canadian Dollar

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getCurrency()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getCurrency())
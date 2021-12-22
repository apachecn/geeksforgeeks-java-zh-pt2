# number format Java 中的 setMinimumIntegerDigits()方法示例

> 原文:[https://www . geesforgeks . org/number format-setminimumentegerdigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setminimumintegerdigits-method-in-java-with-examples/)

**setminimumentegerdigits()**方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，用于设置数字的整数部分允许的最小位数。如果最小值的新值小于最大值的当前值，则最大值也将设置为新值。

**语法:**

```java
public void setMinimumIntegerDigits(int val)
```

**参数**:该功能接受一个强制参数**值**，该值指定要设置的最小值。

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

        System.out.println("Minimum set initially as: "
                           + nF.getMinimumIntegerDigits());

        // Set grouping
        nF.setMinimumIntegerDigits(100);

        // Print the final
        System.out.println("Minimum set finally as: "
                           + nF.getMinimumIntegerDigits());
    }
}
```

**输出:**

```java
Minimum set initially as: 1
Minimum set finally as: 100

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

        System.out.println("Minimum set initially as: "
                           + nF.getMinimumIntegerDigits());

        // Set grouping
        nF.setMinimumIntegerDigits(1);

        // Print the final
        System.out.println("Minimum set finally as: "
                           + nF.getMinimumIntegerDigits());
    }
}
```

**输出:**

```java
Minimum set initially as: 1
Minimum set finally as: 1

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # setminimumentegerdigits(int)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#setMinimumIntegerDigits(int))
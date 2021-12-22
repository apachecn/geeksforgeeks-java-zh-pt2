# Java 中 NumberFormat getRoundingMode()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getroundingmode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getroundingmode-method-in-java-with-examples/)

**getRoundingMode()** 方法是**[Java . text . Number Format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，返回给定数字格式中正在使用的舍入模式。

**语法** :

```java
public RoundingMode getRoundingMode()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回用于该数字格式的舍入模式。

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

        // Get the instance for Locale US
        NumberFormat nF
            = NumberFormat.getInstance(
                Locale.US);

        // Prints the Rounding Mode
        System.out.println("The rounding mode"
                           + " value is: "
                           + nF.getRoundingMode());
    }
}
```

**输出:**

```java
The rounding mode value is: HALF_EVEN

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

        // Get the instance for Locale CANADA
        NumberFormat nF
            = NumberFormat.getInstance(
                Locale.CANADA);

        // Prints the Rounding Mode
        System.out.println("The rounding mode"
                           + " value is: "
                           + nF.getRoundingMode());
    }
}
```

**输出:**

```java
The rounding mode value is: HALF_EVEN

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getRoundingMode()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getRoundingMode())
# Java 中 NumberFormat setRoundingMode()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-setroundingmode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setroundingmode-method-in-java-with-examples/)

**设置舍入模式()**方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，用于设置此 NumberFormat 中使用的舍入模式。处理不同舍入模式的子类应该覆盖这个方法。

**语法:**

```java
public void setRoundingMode(RoundingMode mode)
```

**参数**:该功能接受一个强制参数**模式**，指定要设置的模式。

**返回值**:该函数不返回任何内容，因此返回类型为 void。

**异常:**函数抛出两个异常，描述如下:

*   *不支持操作异常*:如果默认实现总是抛出这个异常
*   *空指针异常*:如果舍入模式为空

下面是上述功能的实现:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;
import java.math.RoundingMode;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        NumberFormat nF
            = NumberFormat.getNumberInstance();

        System.out.println("set initially as: "
                           + nF.getRoundingMode());

        // Set grouping
        nF.setRoundingMode(RoundingMode.FLOOR);

        // Print the final
        System.out.println("set finally as: "
                           + nF.getRoundingMode());
    }
}
```

**Output:** 

```java
set initially as: HALF_EVEN
set finally as: FLOOR
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;
import java.math.RoundingMode;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        NumberFormat nF
            = NumberFormat.getNumberInstance();

        System.out.println("set initially as: "
                           + nF.getRoundingMode());

        // Set grouping
        nF.setRoundingMode(RoundingMode.DOWN);

        // Print the final
        System.out.println("set finally as: "
                           + nF.getRoundingMode());
    }
}
```

**Output:** 

```java
set initially as: HALF_EVEN
set finally as: DOWN
```

**程序 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.util.Currency;
import java.math.RoundingMode;

public class Main {
    public static void main(String[] args)
        throws Exception
    {
        try {

            NumberFormat nF
                = NumberFormat.getNumberInstance();

            System.out.println("set initially as: "
                               + nF.getRoundingMode());

            // Set grouping
            nF.setRoundingMode(null);

            // Print the final
            System.out.println("set finally as: "
                               + nF.getRoundingMode());
        }
        catch (Exception e) {
            System.out.println("Exception is: "
                               + e);
        }
    }
}
```

**Output:** 

```java
set initially as: HALF_EVEN
Exception is: java.lang.NullPointerException
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/math/roundingmode . html](https://docs.oracle.com/javase/10/docs/api/java/math/RoundingMode.html)
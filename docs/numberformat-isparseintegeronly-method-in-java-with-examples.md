# NumberFormat 是 Java 中的 isParseIntegerOnly()方法，带有示例

> 原文:[https://www . geeksforgeeks . org/number format-isparseintegeronly-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-isparseintegeronly-method-in-java-with-examples/)

**ispareintegeronly()**方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，如果数字被解析为这种格式的整数，则返回 true。例如，在英语区域设置中，当 ParseIntegerOnly 为 true 时，字符串“5678”将被解析为整数值 5678，解析将停止在“.”性格。

**语法:**

```java
public boolean isParseIntegerOnly()
```

**参数**:该功能不接受任何参数。

**返回值**:函数返回一个布尔值，如果数字可以解析为整数，则返回 true，否则返回 false。

下面是上述功能的实现:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

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
            = NumberFormat
                  .getPercentInstance(
                      Locale.US);

        // Check
        if (nF.isParseIntegerOnly())
            System.out.println("isParseIntegerOnly: Yes");
        else
            System.out.println("isParseIntegerOnly: No");
    }
}
```

**Output:** 

```java
isParseIntegerOnly: No
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            = NumberFormat
                  .getPercentInstance(
                      Locale.CANADA);

        // Check
        if (nF.isParseIntegerOnly())
            System.out.println("isParseIntegerOnly: Yes");
        else
            System.out.println("isParseIntegerOnly: No");
    }
}
```

**Output:** 

```java
isParseIntegerOnly: No
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # isparseinetegeronly()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#isParseIntegerOnly())T4】
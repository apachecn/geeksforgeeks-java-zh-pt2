# Java 中的 NumberFormat setParseIntegerOnly()方法，带示例

> 原文:[https://www . geeksforgeeks . org/number format-setparsentegeronly-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-setparseintegeronly-method-in-java-with-examples/)

**setParseIntegerOnly()** 方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，该方法设置数字是否只应被解析为整数。

**语法:**

```java
public void setParseIntegerOnly(boolean val)
```

**参数**:该功能接受一个强制参数**值**，该值指定要设置的值

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

        System.out.println("set initially as: "
                           + nF.isParseIntegerOnly());

        // Set grouping
        nF.setParseIntegerOnly(false);

        // Print the final
        System.out.println("set finally as: "
                           + nF.isParseIntegerOnly());
    }
}
```

**输出:**

```java
set initially as: false
set finally as: false

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

        System.out.println("set initially as: "
                           + nF.isParseIntegerOnly());

        // Set grouping
        nF.setParseIntegerOnly(true);

        // Print the final
        System.out.println("set finally as: "
                           + nF.isParseIntegerOnly());
    }
}
```

**输出:**

```java
set initially as: false
set finally as: true

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # setParseIntegerOnly(布尔型)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#setParseIntegerOnly(boolean))
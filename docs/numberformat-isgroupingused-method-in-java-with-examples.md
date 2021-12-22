# NumberFormat 是 Java 中的 roupingUsed()方法，带有示例

> 原文:[https://www . geesforgeks . org/number format-is grouping used-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-isgroupingused-method-in-java-with-examples/)

**isGroupingUsed()** 方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，如果给定格式中使用了分组，则返回 true，否则返回 false。数字 567879 在英语语言环境中的分组可以用“5，67，879”来完成，其中大小取决于语言环境并由其子类决定

**语法** :

```
public boolean isGroupingUsed()
```

**参数**:该功能不接受任何参数。

**返回值**:函数返回一个布尔值，如果分组可以用这种格式，则返回 true，否则返回 false。

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

        // Get the instance for Locale US
        NumberFormat nF
            = NumberFormat
                  .getPercentInstance(
                      Locale.US);

        // Prints the hash-code value
        if (nF.isGroupingUsed())
            System.out.println("Yes!"
                               + " grouping is used");
        else
            System.out.println("No!"
                               + " grouping is used");
    }
}
```

**输出:**

```
Yes! grouping is used

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

        // Get the instance for Locale CANADA
        NumberFormat nF
            = NumberFormat
                  .getPercentInstance(
                      Locale.CANADA);

        // Prints the hash-code value
        if (nF.isGroupingUsed())
            System.out.println("Yes! "
                               + "grouping is used");
        else
            System.out.println("No! "
                               + "grouping is used");
    }
}
```

**输出:**

```
Yes! grouping is used

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # isgrouping used()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#isGroupingUsed())
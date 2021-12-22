# Java 中的 NumberFormat hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-hashcode-method-in-java-with-examples/)

**hashCode()** 方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，为这个给定的实例对象返回一个 hash-code 值。

**语法** :

```java
public int hashCode()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回哈希码值。

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
            = NumberFormat
                  .getInstance(Locale.US);

        // Prints the hash-code value
        System.out.println("The hash-code values is: "
                           + nF.hashCode());
    }
}
```

**输出:**

```java
The hash-code values is: 423132

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

        // Get the instance for Locale US
        NumberFormat nF
            = NumberFormat
                  .getInstance(Locale.US);

        // Prints the hash-code value
        System.out.println("The hash-code values is: "
                           + nF.hashCode());
    }
}
```

**输出:**

```java
The hash-code values is: 423132

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#hashCode())
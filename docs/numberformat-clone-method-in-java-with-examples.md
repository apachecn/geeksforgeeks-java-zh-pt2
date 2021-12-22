# Java 中的 NumberFormat 克隆()方法，示例

> 原文:[https://www . geesforgeks . org/number format-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-clone-method-in-java-with-examples/)

**clone()** 方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，它返回一个定义任何给定实例的克隆的对象。

**语法** :

```java
public Object clone()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个定义任意给定实例克隆的对象。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to implement
// the above function
import java.text.NumberFormat;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the percent Instance
        NumberFormat nF
            = NumberFormat
                  .getPercentInstance();

        // Print the clone of this instance
        System.out.println(nF.clone());
    }
}
```

**输出:**

```java
java.text.DecimalFormat@674dc

```

**程序二:**

```java
// Java program to implement
// the above function

import java.text.NumberFormat;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the Currency Instance
        NumberFormat nF
            = NumberFormat
                  .getCurrencyInstance();

        // Print the clone of this instance
        System.out.println(nF.clone());
    }
}
```

**输出:**

```java
java.text.DecimalFormat@67500

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # clone()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#clone())
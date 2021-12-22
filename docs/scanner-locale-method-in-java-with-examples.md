# Java 中的扫描器 locale()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-locale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-locale-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **locale()** 方法返回该扫描仪的区域设置。

**语法:**

```java
public Locale locale()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回该**扫描仪的区域设置**

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// locale() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Gfg Geeks GeeksForGeeks";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print the locale
        System.out.println(scanner.locale());

        scanner.close();
    }
}
```

**输出:**

```java
en_US

```

**程序二:**

```java
// Java program to illustrate the
// locale() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "121324";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print the locale
        System.out.println(scanner.locale());

        scanner.close();
    }
}
```

**输出:**

```java
en_US

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # locale()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#locale())
# Java 中 Scanner useLocale()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-uselocale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-uselocale-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **useLocale()** 方法将该扫描仪的区域设置为指定的区域设置。

**语法:**

```
public Scanner useLocale(Locale locale)
```

**参数:**该函数接受一个强制参数**区域设置**，该参数指定了一个指定要使用的区域设置的字符串。

**返回值:**该功能返回该**改装扫描仪**。

**例外:**如果基数小于*字符。最小基数*或大于*字符。MAX_RADIX* ，则抛出 *IllegalArgumentException* 。

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// Scanner useLocale() method in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Geeksforgeeks has Scanner Class Methods";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print a line of the scanner
        System.out.println("Scanner String: \n"
                           + scanner.nextLine());

        // display the previous locale
        System.out.println("Current Lcoale: "
                           + scanner.locale());

        // change the locale of the scanner
        scanner.useLocale(Locale.ENGLISH);
        System.out.println("Changing Locale to ENGLISH");

        // display the new locale
        System.out.println("Updated Locale: "
                           + scanner.locale());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
Scanner String: 
Geeksforgeeks has Scanner Class Methods
Current Lcoale: en_US
Changing Locale to ENGLISH
Updated Locale: en

```

**程序二:**

```
// Java program to illustrate the
// Scanner useLocale() method in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Geeksforgeeks 2018";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print a line of the scanner
        System.out.println("Scanner String: \n"
                           + scanner.nextLine());

        // display the previous locale
        System.out.println("Current Lcoale: "
                           + scanner.locale());

        // change the locale of the scanner
        scanner.useLocale(Locale.FRENCH);
        System.out.println("Changing Locale to FRENCH");

        // display the new locale
        System.out.println("Updated Locale: "
                           + scanner.locale());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
Scanner String: 
Geeksforgeeks 2018
Current Lcoale: en_US
Changing Locale to FRENCH
Updated Locale: fr

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # useLocale(Java . util . locale)](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#useLocale(java.util.Locale))
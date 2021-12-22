# Java 中扫描仪复位()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-reset-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **reset()** 方法重置此扫描仪。在重置扫描仪时，它**会丢弃**所有的显式状态信息，这些信息可能已经通过调用**useDelimiter(Java . util . regex . pattern)、useLocale(java.util.Locale)或 useRadix(int)而改变。**

**语法:**

```
public Scanner reset()
```

**返回值:**该功能返回已复位的**扫描仪**。

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// reset() method of Scanner class in Java

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
        System.out.println("Scanner String:\n"
                           + scanner.nextLine());

        // change the locale of this scanner
        scanner.useLocale(Locale.US);

        // change the radix of this scanner
        scanner.useRadix(30);

        System.out.println("\nBefore Reset:\n");

        // print the values before reset
        System.out.println("Radix: " + scanner.radix());
        System.out.println("Locale: " + scanner.locale());

        // reset
        scanner.reset();

        System.out.println("\nAfter Reset:\n");

        System.out.println("Radix: " + scanner.radix());
        System.out.println("Locale: " + scanner.locale());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
Scanner String:
Geeksforgeeks has Scanner Class Methods

Before Reset:

Radix: 30
Locale: en_US

After Reset:

Radix: 10
Locale: en_US

```

**程序二:**

```
// Java program to illustrate the
// reset() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Geeksforgeeks";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print a line of the scanner
        System.out.println("Scanner String:\n"
                           + scanner.nextLine());

        // change the locale of this scanner
        scanner.useLocale(Locale.US);

        // change the radix of this scanner
        scanner.useRadix(12);

        System.out.println("\nBefore Reset:\n");

        // print the values before reset
        System.out.println("Radix: " + scanner.radix());
        System.out.println("Locale: " + scanner.locale());

        // reset
        scanner.reset();

        System.out.println("\nAfter Reset:\n");

        System.out.println("Radix: " + scanner.radix());
        System.out.println("Locale: " + scanner.locale());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
Scanner String:
Geeksforgeeks

Before Reset:

Radix: 12
Locale: en_US

After Reset:

Radix: 10
Locale: en_US

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # reset()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#reset())
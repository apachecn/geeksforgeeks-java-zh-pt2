# Java 中的 Scanner useRadix()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-user adix-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-useradix-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **useRadix(基数)**方法将该扫描仪的默认基数设置为指定基数。扫描仪的基数会影响与正则表达式匹配的默认数字的元素。

**语法:**

```java
public Scanner useRadix(int radix)
```

**参数:**该函数接受一个强制参数*基数*，该参数指定扫描数字时使用的基数。

**返回值:**函数返回这个**扫描仪对象。**

**例外:**如果基数小于*字符。最小基数*或大于*字符。MAX_RADIX* ，则抛出 *IllegalArgumentException* 。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// useRadix() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "Geeksforgeeks has Scanner Class Methods";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // print the line of the scanner
            System.out.println("String:\n"
                               + scanner.nextLine());

            // display the Old radix
            System.out.println("\nOld Radix: "
                               + scanner.radix());

            // change the radix
            // of the scanner to 12
            scanner.useRadix(12);

            // display the new radix
            System.out.println("\nNew Radix: "
                               + scanner.radix());

            // close the scanner
            scanner.close();
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
String:
Geeksforgeeks has Scanner Class Methods

Old Radix: 10

New Radix: 12

```

**程序二:**异常演示

```java
// Java program to illustrate the
// useRadix() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "Geeksforgeeks has Scanner Class Methods";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // print the line of the scanner
            System.out.println("String:\n"
                               + scanner.nextLine());

            // display the Old radix
            System.out.println("\nOld Radix: "
                               + scanner.radix());

            // change the radix
            // of the scanner to 64
            scanner.useRadix(64);

            // display the new radix
            System.out.println("\nNew Radix: "
                               + scanner.radix());

            // close the scanner
            scanner.close();
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
String:
Geeksforgeeks has Scanner Class Methods

Old Radix: 10
Exception thrown : java.lang.IllegalArgumentException: radix:64

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # useRadix(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#useRadix(int))
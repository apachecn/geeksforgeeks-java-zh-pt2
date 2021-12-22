# Java 中的扫描仪关闭()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-close-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **close()** 方法关闭已经打开的扫描仪。如果扫描仪已经关闭，那么在调用此方法时，它将不起作用。

**语法:**

```java
public void close()
```

**返回值:**函数不返回值。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// close() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Get the string
            String s = "Geeksforgeeks has Scanner Class Methods";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // print the next line of the string
            System.out.println("Scanner: "
                               + scanner.nextLine());

            // close the scanner
            scanner.close();

            System.out.println("\nScanner Closed.\n");

            System.out.println("Trying to use scanner"
                               + " after closing.");

            // print the next line of the string
            System.out.println(scanner.nextLine());
        }

        catch (Exception e) {
            System.out.println("Exception thrown:\n" + e);
        }
    }
}
```

**输出:**

```java
Scanner: Geeksforgeeks has Scanner Class Methods

Scanner Closed.

Trying to use scanner after closing.
Exception thrown:
java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # close()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#close())
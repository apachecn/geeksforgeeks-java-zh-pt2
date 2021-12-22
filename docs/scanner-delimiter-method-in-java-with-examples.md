# Java 中的扫描器定界符()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-delimiter-in-Java-method-with-examples/](https://www.geeksforgeeks.org/scanner-delimiter-method-in-java-with-examples/)

**[Java . util . Scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的**分隔符()**方法返回此 Scanner 当前用于匹配分隔符的模式。

**语法:**

```java
public Pattern delimiter()
```

**返回值:**该函数返回扫描仪的*定界*模式。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// delimiter() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Geeksforgeeks has Scanner Class Methods";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // prints the next line of the string
        System.out.println("Scanner String: \n"
                           + scanner.nextLine());

        // print the delimiter this scanner is using
        System.out.println("\nDelimiter being used in Scanner: "
                           + scanner.delimiter());

        // Close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
Scanner String: 
Geeksforgeeks has Scanner Class Methods

Delimiter being used in Scanner: \p{javaWhitespace}+

```

**程序二:**

```java
// Java program to illustrate the
// delimiter() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Geeksforgeeks.has.Scanner.Class.Methods";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // Set the delimiter to "."
        scanner.useDelimiter(".");

        // prints the next line of the string
        System.out.println("Scanner String: \n"
                           + scanner.nextLine());

        // print the delimiter this scanner is using
        System.out.println("\nDelimiter being used in Scanner: "
                           + scanner.delimiter());

        // Close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
Scanner String: 
Geeksforgeeks.has.Scanner.Class.Methods

Delimiter being used in Scanner: .

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # delimiter()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#delimiter())
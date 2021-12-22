# Java 中的扫描仪基数()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-radix-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-radix-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的**基数()**方法返回该扫描仪的默认基数。

**语法:**

```java
public int radix()
```

**返回值:**该函数返回该扫描仪的**默认基数**。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// radix() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Geeksforgeeks has Scanner methods";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print a line of the scanner
        System.out.println("Scanner String:\n"
                           + scanner.nextLine());

        // print the default radix
        System.out.println("Default Radix value: "
                           + scanner.radix());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
Scanner String:
Geeksforgeeks has Scanner methods
Default Radix value: 10

```

**程序二:**

```java
// Java program to illustrate the
// radix() method of Scanner class in Java

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
        System.out.println("Scanner String: "
                           + scanner.nextLine());

        // print the default radix
        System.out.println("Default Radix value: "
                           + scanner.radix());

        // change the radix of this scanner
        scanner.useRadix(30);

        System.out.println("Radix changed to 30");

        // print the default radix
        System.out.println("Default Radix value: "
                           + scanner.radix());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
Scanner String: Geeksforgeeks
Default Radix value: 10
Radix changed to 30
Default Radix value: 30

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # radix()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#radix())
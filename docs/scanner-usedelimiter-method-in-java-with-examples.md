# 扫描仪使用 Java 中的 elimiter()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-usedelimiter-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-usedelimiter-method-in-java-with-examples/)

### 图案图案

类的 [**的**useDelimiter(Pattern Pattern)**方法将该扫描仪的定界模式设置为指定模式。**](https://www.geeksforgeeks.org/scanner-class-in-java/)

**语法:**

```
public Scanner useDelimiter(Pattern pattern)

```

**参数:**该函数接受指定定界模式的强制参数**模式**。

**返回值:**功能返回**这台扫描仪**。

以下程序说明了上述功能:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the useDelimiter(Pattern Pattern)
// method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

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

        // display the old delimiter
        System.out.println("Old delimiter: "
                           + scanner.delimiter());

        // change the delimiter of this scanner
        scanner.useDelimiter(Pattern.compile(".ll."));

        // display the new delimiter
        System.out.println("New delimiter: "
                           + scanner.delimiter());

        // close the scanner
        scanner.close();
    }
}
```

**Output:** 

```
Scanner String: 
Geeksforgeeks has Scanner Class Methods
Old delimiter: \p{javaWhitespace}+
New delimiter: .ll.

```

### 字符串模式

类的 [**方法将该扫描仪的定界模式设置为由指定字符串构造的模式。**](https://www.geeksforgeeks.org/scanner-class-in-java/)

**语法:**

```
public Scanner useDelimiter(String pattern)

```

**参数:**该函数接受指定定界模式的强制参数字符串**模式**。

**返回值:**功能返回**这台扫描仪**。

以下程序说明了上述功能:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the useDelimter(String Pattern)
// method of Scanner class in Java

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

        // print the old delimiter
        System.out.println("Old Delimiter: "
                           + scanner.delimiter());

        // change the delimiter
        scanner.useDelimiter("Wor");

        // print the new delimiter
        System.out.println("New Delimiter: "
                           + scanner.delimiter());

        // close the scanner
        scanner.close();
    }
}
```

**Output:** 

```
Scanner String: 
Geeksforgeeks has Scanner Class Methods
Old Delimiter: \p{javaWhitespace}+
New Delimiter: Wor

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # useDelimiter(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#useDelimiter(java.lang.String))
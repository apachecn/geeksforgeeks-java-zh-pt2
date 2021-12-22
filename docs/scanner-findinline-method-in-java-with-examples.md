# Java 中 Scanner findInLine()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-find inline-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-findinline-method-in-java-with-examples/)

### 查找内嵌(模式模式)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的**find inline(Pattern Pattern)**方法尝试忽略分隔符查找指定模式的下一个匹配项。如果在下一个行分隔符之前找到了模式，扫描仪将前进到匹配的输入，并返回与模式匹配的字符串。如果在直到下一行分隔符的输入中没有检测到这样的模式，则返回 null，扫描仪的位置不变。

**语法:**

```java
public String findInLine(Pattern pattern)
```

**参数:**该功能接受强制参数“图案”*图案*，即扫描的图案。

**返回值:**该函数返回扫描仪的*定界*模式。

**异常:**如果扫描仪关闭，该功能将抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// findInLine() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Get the string to be searched
            String s = "Geeksforgeeks has Scanner Class Methods";

            // Print the string
            System.out.println("Target String:\n" + s);

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // finds a pattern of any 5 letter plus "for"
            System.out.println("\nAny 5 letter plus for : "
                               + scanner.findInLine(
                                     Pattern.compile(".....for")));

            // close the scanner
            scanner.close();
        }
        catch (IllegalStateException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Target String:
Geeksforgeeks has Scanner Class Methods

Any 5 letter plus for : Geeksfor

```

**程序 2:** 演示**非法状态异常**

```java
// Java program to illustrate the
// findInLine() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Get the string to be searched
            String s = "Geeksforgeeks has Scanner Class Methods";

            // Print the string
            System.out.println("Target String:\n" + s);

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // close the scanner
            scanner.close();

            // finds a pattern of any 5 letter plus "for"
            System.out.println("\nAny 5 letter plus for : "
                               + scanner.findInLine(
                                     Pattern.compile(".....for")));

            // print the next line of the string
            System.out.println("" + scanner.nextLine());
        }
        catch (IllegalStateException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
Target String:
Geeksforgeeks has Scanner Class Methods
Exception thrown:
 java.lang.IllegalStateException:
 Scanner closed

```

### 查找内联(字符串模式)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的**find inline(String pattern)**方法尝试查找由指定字符串模式构造的模式的下一个匹配项，忽略分隔符。

**语法:**

```java
public String findInLine(String pattern)
```

**参数:**该功能接受扫描的强制参数字符串*模式*。

**返回值:**该函数返回扫描仪的*定界*模式。

**异常:**如果扫描仪关闭，该功能将抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// findInLine() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Get the string to be searched
            String s = "Geeksforgeeks has Scanner Class Methods";

            // Print the string
            System.out.println("Target String:\n" + s);

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // finds a pattern of any 5 letter plus "for"
            System.out.println("\nAny 5 letter plus for : "
                               + scanner.findInLine(
                                     Pattern.compile(".....for")));

            // close the scanner
            scanner.close();
        }

        catch (IllegalStateException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Target String:
Geeksforgeeks has Scanner Class Methods

Any 5 letter plus for : Geeksfor

```

**程序 2:** 演示**非法状态异常**

```java
// Java program to illustrate the
// findInLine() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Get the string to be searched
            String s = "Geeksforgeeks has Scanner Class Methods";

            // Print the string
            System.out.println("Target String:\n" + s);

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // close the scanner
            scanner.close();

            // finds a pattern of any 5 letter plus "for"
            System.out.println("\nAny 5 letter plus for : "
                               + scanner.findInLine(
                                     Pattern.compile(".....for")));
        }

        catch (IllegalStateException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Target String:
Geeksforgeeks has Scanner Class Methods
Exception thrown :
 java.lang.IllegalStateException:
 Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # find inline(Java . util . regex . pattern)](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#findInLine(java.util.regex.Pattern))
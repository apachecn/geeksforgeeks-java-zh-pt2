# Java 中的 Scanner skip()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-skip-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-skip-method-in-java-with-examples/)

### 跳过(模式模式)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **skip(Pattern pattern)** 方法跳过与指定模式匹配的输入，忽略分隔符。如果指定模式的锚定匹配成功，函数将跳过输入。

**语法:**

```java
public Scanner skip(Pattern pattern)
```

**参数:**该函数接受一个强制参数**模式**，它指定一个字符串作为要跳过的模式。

**返回值:**该函数返回该扫描仪

**异常:**此方法抛出以下异常:

*   [T0】 nosucheelementexception 【T1]: When the specified pattern is not found.
*   非法状态异常:-你好-你好

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// skip() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "GeeksForGeeks - "
                   + "A Computer Science Portal for Geeks";

        System.out.println("String trying to get input:\n"
                           + s);

        // create a new scanner with
        // the specified String Object
        Scanner scanner = new Scanner(s);

        // skip the word that
        // matches with the pattern ..eks
        System.out.println("Skipping 5 letter words"
                           + " that ends with 'eks'\n");

        scanner.skip(Pattern.compile("..eks"));

        // print a line of the scanner
        System.out.println("Input Scanner String: \n"
                           + scanner.nextLine());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
String trying to get input:
GeeksForGeeks - A Computer Science Portal for Geeks
Skipping 5 letter words that ends with 'eks'

Input Scanner String: 
ForGeeks - A Computer Science Portal for Geeks

```

**程序 2:** 演示 nosucheelementexception

```java
// Java program to illustrate the
// skip() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {
            String s = "GeeksForGeeks - "
                       + "A Computer Science Portal for Geeks";

            System.out.println("String trying to get input:\n"
                               + s);

            // create a new scanner with
            // the specified String Object
            Scanner scanner = new Scanner(s);

            // skip the word that
            // matches with the pattern and
            System.out.println("Skipping 3 letter words"
                               + " and\n");

            scanner.skip(Pattern.compile("and"));

            // print a line of the scanner
            System.out.println("Input Scanner String: \n"
                               + scanner.nextLine());

            // close the scanner
            scanner.close();
        }

        catch (Exception e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
String trying to get input:
GeeksForGeeks - A Computer Science Portal for Geeks
Skipping 3 letter words and

Exception thrown: java.util.NoSuchElementException

```

**程序 3:** 演示非法状态异常

```java
// Java program to illustrate the
// skip() method of Scanner class in Java

import java.util.*;
import java.util.regex.Pattern;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {
            String s = "GeeksForGeeks - "
                       + "A Computer Science Portal for Geeks";

            System.out.println("String trying to get input:\n"
                               + s);

            // create a new scanner with
            // the specified String Object
            Scanner scanner = new Scanner(s);

            // close the scanner
            scanner.close();
            System.out.println("Scanner Closed");

            // skip the word that
            // matches with the pattern and
            System.out.println("Trying to Skip 3 letter words"
                               + " and\n");

            scanner.skip(Pattern.compile("and"));

            // print a line of the scanner
            System.out.println("Input Scanner String: \n"
                               + scanner.nextLine());
        }

        catch (Exception e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
String trying to get input:
GeeksForGeeks - A Computer Science Portal for Geeks
Scanner Closed
Trying to Skip 3 letter words and

Exception thrown: java.lang.IllegalStateException: Scanner closed

```
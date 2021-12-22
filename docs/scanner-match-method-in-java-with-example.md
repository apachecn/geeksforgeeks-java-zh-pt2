# Java 中扫描仪匹配()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-match-method-in-Java-with-example/](https://www.geeksforgeeks.org/scanner-match-method-in-java-with-example/)

**[Java . util . scanner](https://www.GeeksforGeeks.org/scanner-class-in-java/)**类的 **match()** 方法返回该扫描仪上次扫描操作的匹配结果。

**语法:**

```java
public MatchResult match()
```

**返回值:**该函数返回最后一次匹配操作的**匹配结果**。

**异常**:如果没有进行匹配，或者最后一次匹配不成功，该功能将抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// match() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "GFG Geeks!";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // check if next token is "GFG"
        System.out.println("" + scanner.hasNext("GFG"));

        // find the last match and print it
        System.out.println("" + scanner.match());

        // print the line
        System.out.println("" + scanner.nextLine());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
true
java.util.regex.Matcher[pattern=GFG region=0, 10 lastmatch=GFG]
GFG Geeks!

```

**程序 2:** 演示非法状态异常

```java
// Java program to illustrate the
// match() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "GFG Geeks!";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // check if next token is "gopal"
            System.out.println("" + scanner.hasNext("gopal"));

            // find the last match and print it
            System.out.println("" + scanner.match());

            // print the line
            System.out.println("" + scanner.nextLine());

            // close the scanner
            scanner.close();
        }

        catch (IllegalStateException e) {
            System.out.println("Exception caught is: " + e);
        }
    }
}
```

**输出:**

```java
false
Exception caught is: java.lang.IllegalStateException: No match result available

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # match()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#match())
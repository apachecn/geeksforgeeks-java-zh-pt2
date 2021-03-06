# Scanner 在 Java 中有 NextDouble()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-hasnextdouble-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-hasnextdouble-method-in-java-with-examples/)

如果这个扫描器的输入中的下一个标记可以用 NextDouble()方法解释为 Double，那么这个类的 **hasNextDouble()** 方法返回 true。扫描仪不会前进超过任何输入。

**语法:**

```java
public Double hasNextDouble()
```

**参数:**函数不接受任何参数。

**返回值:**当且仅当该扫描器的下一个令牌是有效的 Double 时，该函数返回 true。

**异常**:如果扫描仪关闭，该功能会抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// hasNextDouble() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "gfg 2 geeks!";

        // new scanner with the
        // specified String Object
        Scanner scanner = new Scanner(s);

        // use US locale to interpret Doubles in a string
        scanner.useLocale(Locale.US);

        // iterate till end
        while (scanner.hasNext()) {

            // check if the scanner's
            // next token is a Double with the default radix
            System.out.print("" + scanner.hasNextDouble());

            // print what is scanned
            System.out.print(" -> " + scanner.next() + "\n");
        }

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
false -> gfg
true -> 2
false -> geeks!

```

**程序二:**程序演示异常

```java
// Java program to illustrate the
// hasNextDouble() method of Scanner class in Java
// Exception case

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {
            String s = "gfg 2 geeks!";

            // new scanner with the
            // specified String Object
            Scanner scanner = new Scanner(s);

            // use US locale to interpret Doubles in a string
            scanner.useLocale(Locale.US);

            scanner.close();

            // iterate till end
            while (scanner.hasNext()) {

                // check if the scanner's
                // next token is a Double with the default radix
                System.out.print("" + scanner.hasNextDouble());

                // print what is scanned
                System.out.print(" -> " + scanner.next() + "\n");
            }

            // close the scanner
            scanner.close();
        }
        catch (IllegalStateException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # hasNextDouble()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#hasNextDouble())
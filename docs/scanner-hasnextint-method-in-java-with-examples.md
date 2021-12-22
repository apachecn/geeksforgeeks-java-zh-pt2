# Java 中 Scanner hasNextInt()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-hasnextint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-hasnextint-method-in-java-with-examples/)

如果这个扫描器的输入中的下一个标记可以被假定为给定基数的 Int 值，那么**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **hasNextInt()** 方法返回 true。扫描仪不会前进超过任何输入。如果没有基数作为参数传递，函数会将基数解释为默认基数，并相应地运行。

**语法:**

```
public boolean hasNextInt(int radix)
            or
public boolean hasNextInt()
```

**参数:**该函数接受单个参数基数，该基数不是强制的。它指定用于将令牌解释为 Int 值的基数。

**返回值:**当且仅当此扫描器的下一个令牌是默认基数中的有效 Int 值时，此函数返回 true。

**异常**:如果扫描仪关闭，该功能会抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// hasNextInt() method of Scanner class in Java
// with parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "gfg 2 geeks!";

        // new scanner with the
        // specified String Object
        Scanner scanner = new Scanner(s);

        // use US locale to interpret Ints in a string
        scanner.useLocale(Locale.US);

        // iterate till end
        while (scanner.hasNext()) {

            // check if the scanner's
            // next token is a Int with a radix 3
            System.out.print("" + scanner.hasNextInt(3));

            // print what is scanned
            System.out.print(" -> " + scanner.next() + "\n");
        }

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
false -> gfg
true -> 2
false -> geeks!

```

**程序二:**

```
// Java program to illustrate the
// hasNextInt() method of Scanner class in Java
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

        // use US locale to interpret Ints in a string
        scanner.useLocale(Locale.US);

        // iterate till end
        while (scanner.hasNext()) {

            // check if the scanner's
            // next token is a Int with the default radix
            System.out.print("" + scanner.hasNextInt());

            // print what is scanned
            System.out.print(" -> " + scanner.next() + "\n");
        }

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
false -> gfg
true -> 2
false -> geeks!

```

**程序 3:** 程序演示异常

```
// Java program to illustrate the
// hasNextInt() method of Scanner class in Java
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

            // use US locale to interpret Ints in a string
            scanner.useLocale(Locale.US);

            scanner.close();

            // iterate till end
            while (scanner.hasNext()) {

                // check if the scanner's
                // next token is a Int with the default radix
                System.out.print("" + scanner.hasNextInt());

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

```
Exception: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # hasNextInt()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#hasNextInt())
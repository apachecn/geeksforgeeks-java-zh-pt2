# 扫描器有 Java 中的 NextBoolean()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-hasnextboolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/scanner-hasnextboolean-method-in-java-with-examples/)

如果扫描仪输入中的下一个标记可以使用 NextBoolean()方法解释为布尔值，则**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **hasNextBoolean()** 方法返回 true。扫描仪不会前进超过任何输入。

**语法:**

```
public boolean hasNextBoolean()
```

**参数:**函数不接受任何参数。

**返回值:**当且仅当该扫描仪的下一个标记是有效的布尔值时，该函数返回真。

**异常**:如果扫描仪关闭，该功能会抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// hasNextBoolean() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "gfg true geeks!";

        // new scanner with the
        // specified String Object
        Scanner scanner = new Scanner(s);

        // use US locale to interpret Booleans in a string
        scanner.useLocale(Locale.US);

        // iterate till end
        while (scanner.hasNext()) {

            // check if the scanner's
            // next token is a Boolean with the default radix
            System.out.print("" + scanner.hasNextBoolean());

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
true -> true
false -> geeks!

```

**程序二:**程序演示异常

```
// Java program to illustrate the
// hasNextBoolean() method of Scanner class in Java
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

            // use US locale to interpret Booleans in a string
            scanner.useLocale(Locale.US);

            scanner.close();

            // iterate till end
            while (scanner.hasNext()) {

                // check if the scanner's
                // next token is a Boolean with the default radix
                System.out.print("" + scanner.hasNextBoolean());

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

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # hasNextBoolean()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#hasNextBoolean())
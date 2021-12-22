# 扫描器有 Java 中的 NextLine()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-hasnextline-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-hasnextline-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **hasNextLine()** 方法，如果这个扫描仪的输入中还有一行，则返回 true。此方法在等待输入时可能会阻塞。扫描仪不会前进超过任何输入。

**语法:**

```
public boolean hasNextLine()
```

**参数:**函数不接受任何参数。

**返回值:**当且仅当该扫描仪有另一行输入时，该函数返回真

**异常**:如果扫描仪关闭，该功能会抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// hasNextLine() method of Scanner class in Java
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

        // use US locale to interpret Lines in a string
        scanner.useLocale(Locale.US);

        // iterate till end
        while (scanner.hasNextLine()) {

            // print what is scanned
            System.out.println(scanner.nextLine());
        }

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
gfg 2 geeks!

```

**程序二:**程序演示异常

```
// Java program to illustrate the
// hasNextLine() method of Scanner class in Java
// without parameter

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

            // use US locale to interpret Lines in a string
            scanner.useLocale(Locale.US);

            scanner.close();

            // iterate till end
            while (scanner.hasNextLine()) {

                // print what is scanned
                System.out.println(scanner.nextLine());
            }

            // close the scanner
            scanner.close();
        }
        catch (IllegalStateException e) {
            System.out.println("Exception is: " + e);
        }
    }
}
```

**输出:**

```
Exception is: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # hasNextLine()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#hasNextLine())
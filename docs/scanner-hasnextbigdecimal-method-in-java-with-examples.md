# 扫描器在 Java 中有 NextBigDecimal()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-hasnextbigdecimal-in-Java-method-with-examples/](https://www.geeksforgeeks.org/scanner-hasnextbigdecimal-method-in-java-with-examples/)

如果此扫描器输入中的下一个标记可以使用 NextBigDecimal()方法解释为 BigDecimal，则**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **hasNextBigDecimal()** 方法返回 true。扫描仪不会前进超过任何输入。

**语法:**

```
public boolean hasNextBigDecimal()
```

**参数:**函数不接受任何参数。

**返回值:**当且仅当此扫描器的下一个标记是有效的 BigDecimal 时，此函数返回 true。

**异常**:如果扫描仪关闭，该功能会抛出*非法状态异常*。

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// hasNextBigDecimal() method of Scanner class in Java
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

        // use US locale to interpret BigDecimals in a string
        scanner.useLocale(Locale.US);

        // iterate till end
        while (scanner.hasNext()) {

            // check if the scanner's
            // next token is a BigDecimal with the default radix
            System.out.print("" + scanner.hasNextBigDecimal());

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

**程序二:**程序演示异常

```
// Java program to illustrate the
// hasNextBigDecimal() method of Scanner class in Java
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

            // use US locale to interpret BigDecimals in a string
            scanner.useLocale(Locale.US);

            scanner.close();

            // iterate till end
            while (scanner.hasNext()) {

                // check if the scanner's
                // next token is a BigDecimal with the default radix
                System.out.print("" + scanner.hasNextBigDecimal());

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

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # hasNextBigDecimal()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#hasNextBigDecimal())
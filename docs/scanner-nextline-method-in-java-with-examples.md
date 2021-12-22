# Java 中的 Scanner nextLine()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next line-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-nextline-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextLine()** 方法使该扫描仪前进通过当前行，并返回跳过的输入。该函数打印当前行的剩余部分，在末尾省略行分隔符。下一个设置为行分隔符之后。由于此方法继续在输入中搜索行分隔符，因此如果不存在行分隔符，它可能会搜索所有输入以寻找要跳过的行。

**语法:**

```
public String nextLine()
```

**参数:**函数不接受任何参数。

**返回值:**该方法返回被跳过的**行**

**异常:**该函数抛出如下所述的两个异常:

*   [T0】 no suchelementexception: 【T1] Throw if no line is found.
*   [T0】 illegalstateeexception: 【T1] Thrown if this scanner is turned off.

以下程序说明了上述功能:

**程序 1:**

```
// Java program to illustrate the
// nextLine() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Gfg \n Geeks \n GeeksForGeeks";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print the next line
        System.out.println(scanner.nextLine());

        // print the next line again
        System.out.println(scanner.nextLine());

        // print the next line again
        System.out.println(scanner.nextLine());

        scanner.close();
    }
}
```

**输出:**

```
Gfg 
 Geeks 
 GeeksForGeeks

```

**程序 2:** 演示 nosucheelementexception

```
// Java program to illustrate the
// nextLine() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            System.out.println(scanner.nextLine());
            scanner.close();
        }
        catch (Exception e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Exception thrown: java.util.NoSuchElementException: No line found

```

**程序 3:** 演示非法状态异常

```
// Java program to illustrate the
// nextLine() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "Gfg";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            scanner.close();

            // Prints the new line
            System.out.println(scanner.nextLine());
            scanner.close();
        }
        catch (Exception e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextLine()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextLine())
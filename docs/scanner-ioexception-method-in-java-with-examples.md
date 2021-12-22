# Java 中的 Scanner ioException()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-ioexception-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-ioexception-method-in-java-with-examples/)

**[Java . util . Scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **ioException()** 方法返回该扫描器的底层可读最后抛出的 *IOException* 。如果不存在此类异常，此方法将返回 null。

**语法:**

```
public IOException ioException()
```

**返回值:**该函数返回该扫描仪可读的最后一个异常**。**

**以下程序说明了上述功能:**

****程序 1:****

```
// Java program to illustrate the
// ioException() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "gfg geeks!";

        // create a new scanner
// with the specified String Object
        Scanner scanner = new Scanner(s);

        // print the line
        System.out.println("" + scanner.nextLine());

        // check if there is an IO exception
        System.out.println("" + scanner.ioException());

        // close the scanner
        scanner.close();
    }
}
```

****输出:**

```
gfg geeks!
null

```

**程序二:**

```
// Java program to illustrate the
// ioException() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "gopal dave!";

        // new scanner with the specified String Object
        Scanner scanner = new Scanner(s);

        // print the line
        System.out.println("" + scanner.nextLine());

        // checks if there is an IO exception
        System.out.println("" + scanner.ioException());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```
gopal dave!
null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # ioException()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#ioException())**
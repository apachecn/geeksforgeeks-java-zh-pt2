# Java 中 Scanner nextDouble()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-nextdouble-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextDouble()** 方法将输入的下一个标记作为 Double 进行扫描。如果翻译成功，扫描仪将通过匹配的输入。

**语法:**

```java
public double nextDouble()
```

**参数:**函数不接受任何参数。

**返回值:**该功能从输入返回**双扫描**。

**异常:**函数抛出如下三个异常:

*   [T0】 inputismatexception: 【T1] If the next tag does not match the Double regular expression or is out of range.
*   [T0】 NoSuchElementException: 【T1] Thrown if the input is exhausted.
*   [T0】 illegalstatexception: 【T1] Thrown if this scanner is closed.

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextDouble() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Gfg 9 + 6 = 12.0";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        while (scanner.hasNext()) {

            // if the next is a Double,
            // print found and the Double
            if (scanner.hasNextDouble()) {
                System.out.println("Found Double value :"
                                   + scanner.nextDouble());
            }

            // if no Double is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found Double() value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Double() value :Gfg
Found Double value :9.0
Not found Double() value :+
Found Double value :6.0
Not found Double() value :=
Found Double value :12.0

```

**程序 2:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextDouble() method of Scanner class in Java
// InputMismatchException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "Gfg 9 + 6 = 12.0";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            while (scanner.hasNext()) {

                // if the next is a Double
                // print found and the Double
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next Double value :"
                                   + scanner.nextDouble());
            }
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
Exception thrown: java.util.InputMismatchException

```

**程序 3:** 演示 nosucheelementexception

```java
// Java program to illustrate the
// nextDouble() method of Scanner class in Java
// NoSuchElementException

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

            // Trying to get the next Double value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a Double,
                // print found and the Double
                if (scanner.hasNextDouble()) {
                    System.out.println("Found Double value :"
                                       + scanner.nextDouble());
                }

                // if no Double is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Double value :"
                                       + scanner.next());
                }
            }
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
Not found Double value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 4:** 演示非法状态异常

```java
// Java program to illustrate the
// nextDouble() method of Scanner class in Java
// IllegalStateException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            String s = "Gfg 9 + 6 = 12.0";

            // create a new scanner
            // with the specified String Object
            Scanner scanner = new Scanner(s);

            // close the scanner
            scanner.close();
            System.out.println("Scanner Closed");

            System.out.println("Trying to get "
                               + "next Double value");

            while (scanner.hasNext()) {

                // if the next is a Double,
                // print found and the Double
                if (scanner.hasNextDouble()) {
                    System.out.println("Found Double value :"
                                       + scanner.nextDouble());
                }

                // if no Double is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Double value :"
                                       + scanner.next());
                }
            }
        }
        catch (Exception e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
Scanner Closed
Trying to get next Double value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextDouble()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextDouble())
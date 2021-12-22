# Java 中 Scanner nextLong()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-nextlong-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextLong(基数)**方法将输入的下一个标记扫描为 Long。如果翻译成功，扫描仪将通过匹配的输入。如果参数基数没有被传递，那么它的行为类似于 nextLong(基数)，其中基数被假定为默认基数。

**语法:**

```java
public long nextLong()
```

**参数:**函数接受一个参数**基数**，用于将令牌解释为长值。

**返回值:**该函数返回从输入开始的长扫描。

**异常:**函数抛出如下三个异常:

*   [T0】 inputismatexception: 【T1] If the next tag does not match the Integer regular expression or is out of range.
*   [T0】 NoSuchElementException: 【T1] Thrown if the input is exhausted.
*   [T0】 illegalstatexception: 【T1] Thrown if this scanner is closed.

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextLong() method of Scanner class in Java
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

            // if the next is a Long,
            // print found and the Long
            if (scanner.hasNextLong()) {
                System.out.println("Found Long value :"
                                   + scanner.nextLong());
            }

            // if no Long is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found Long value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Long value :Gfg
Found Long value :9
Not found Long value :+
Found Long value :6
Not found Long value :=
Not found Long value :12.0

```

**程序二:**

```java
// Java program to illustrate the
// nextLong() method of Scanner class in Java
// with parameter

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

            // if the next is a Long,
            // print found and the Long
            if (scanner.hasNextLong()) {
                System.out.println("Found Long value :"
                                   + scanner.nextLong(12));
            }

            // if no Long is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found Long value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Long value :Gfg
Found Long value :9
Not found Long value :+
Found Long value :6
Not found Long value :=
Not found Long value :12.0

```

**程序 3:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextLong() method of Scanner class in Java
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

                // if the next is a Long,
                // print found and the Long
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next Long value :"
                                   + scanner.nextLong());
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

**程序 4:** 演示 nosucheelementexception

```java
// Java program to illustrate the
// nextLong() method of Scanner class in Java
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

            // Trying to get the next Long value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a Long,
                // print found and the Long
                if (scanner.hasNextLong()) {
                    System.out.println("Found Long value :"
                                       + scanner.nextLong());
                }

                // if no Long is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Long value :"
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
Not found Long value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 5:** 演示非法状态异常

```java
// Java program to illustrate the
// nextLong() method of Scanner class in Java
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
                               + "next Long value");

            while (scanner.hasNext()) {

                // if the next is a Long,
                // print found and the Long
                if (scanner.hasNextLong()) {
                    System.out.println("Found Long value :"
                                       + scanner.nextLong());
                }

                // if no Long is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Long value :"
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
Trying to get next Long value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextLong(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextLong(int))
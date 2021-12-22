# Java 中 Scanner nextBigInteger()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next big integer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/scanner-nextbiginteger-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextBigInteger(基数)**方法将输入的下一个标记作为 BigInteger 进行扫描。如果翻译成功，扫描仪将通过匹配的输入。如果参数基数没有被传递，那么它的行为类似于 nextBigInteger(基数)，其中基数被假定为默认基数。

**语法:**

```java
public BigInteger nextBigInteger()
```

**参数:**该函数接受一个参数**基数**，该参数用于将令牌设置为一个大整数值。

**返回值:**该函数从输入中返回**扫描的大整数**。

**异常:**函数抛出如下三个异常:

*   [T0】 inputismattechexception: 【T1] If the next tag does not match the BigIntegereger regular expression or is out of range.
*   [T0】 nosucheelementexception: 【T1] Thrown if the input is exhausted.
*   [T0】 illegalstatexception: 【T1] Thrown if this scanner is closed.

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextBigInteger() method of Scanner class in Java
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

            // if the next is a BigInteger,
            // prBigInteger found and the BigInteger
            if (scanner.hasNextBigInteger()) {
                System.out.println("Found BigInteger value : "
                                   + scanner.nextBigInteger());
            }

            // if no BigInteger is found,
            // prBigInteger "Not Found:" and the token
            else {
                System.out.println("Not found BigInteger value : "
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found BigInteger value :G fg
Found BigInteger value : 9
Not found BigInteger value : +
Found BigInteger value : 6
Not found BigInteger value : =
Not found BigInteger value : 12.0

```

**程序二:**

```java
// Java program to illustrate the
// nextBigInteger() method of Scanner class in Java
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

            // if the next is a BigInteger,
            // prBigInteger found and the BigInteger
            if (scanner.hasNextBigInteger()) {
                System.out.println("Found BigInteger value : "
                                   + scanner.nextBigInteger(12));
            }

            // if no BigInteger is found,
            // prBigInteger "Not Found:" and the token
            else {
                System.out.println("Not found BigInteger value : "
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found BigInteger value : Gfg
Found BigInteger value : 9
Not found BigInteger value : +
Found BigInteger value : 6
Not found BigInteger value : =
Not found BigInteger value : 12.0

```

**程序 3:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextBigInteger() method of Scanner class in Java
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

                // if the next is a BigInteger,
                // prBigInteger found and the BigInteger
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next BigInteger value :"
                                   + scanner.nextBigInteger());
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
// nextBigInteger() method of Scanner class in Java
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

            // Trying to get the next BigInteger value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a BigInteger,
                // prBigInteger found and the BigInteger
                if (scanner.hasNextBigInteger()) {
                    System.out.println("Found BigInteger value :"
                                       + scanner.nextBigInteger());
                }

                // if no BigInteger is found,
                // prBigInteger "Not Found:" and the token
                else {
                    System.out.println("Not found BigInteger value :"
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
Not found BigInteger value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 5:** 演示非法状态异常

```java
// Java program to illustrate the
// nextBigInteger() method of Scanner class in Java
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
                               + "next BigInteger value");

            while (scanner.hasNext()) {

                // if the next is a BigInteger,
                // prBigInteger found and the BigInteger
                if (scanner.hasNextBigInteger()) {
                    System.out.println("Found BigInteger value :"
                                       + scanner.nextBigInteger());
                }

                // if no BigInteger is found,
                // prBigInteger "Not Found:" and the token
                else {
                    System.out.println("Not found BigInteger value :"
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
Trying to get next BigInteger value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextBigInteger(int)](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextBigInteger(int))
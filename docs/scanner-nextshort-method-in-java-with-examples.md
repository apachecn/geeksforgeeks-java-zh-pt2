# Java 中 Scanner nextShort()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next short-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-nextshort-method-in-java-with-examples/)

[**Java . util . scanner**](https://www.geeksforgeeks.org/scanner-class-in-java/)类的 **nextShort(基数)**方法将输入的下一个标记扫描为 Short。如果翻译成功，扫描仪将通过匹配的输入。如果参数基数没有被传递，那么它的行为类似于 nextShort(基数)，其中基数被假定为默认基数。

**语法:**

```java
public short nextShort()

```

**参数:**函数接受一个参数**基数**，用于将令牌解释为一个短值。

**返回值:**该函数返回从输入端扫描的短路。

**异常:**函数抛出三个异常，如下所述:

*   **inputismatchexception:**如果下一个标记与 Integer 正则表达式不匹配，或者超出范围
*   **nosucheelementexception:**如果输入用尽，抛出
*   **illegalstatexception:**如果扫描仪关闭，则抛出

以下程序说明了上述功能:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// nextShort() method of Scanner class in Java
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

            // if the next is a short,
            // print found and the short
            if (scanner.hasNextShort()) {
                System.out.println("Found Short value :"
                                   + scanner.nextShort());
            }

            // if no short is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found short value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**Output:** 

```java
Not found short value :Gfg
Found Short value :9
Not found short value :+
Found Short value :6
Not found short value :=
Not found short value :12.0

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// nextShort() method of Scanner class in Java
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

            // if the next is a short,
            // print found and the short
            if (scanner.hasNextShort()) {
                System.out.println("Found Short value :"
                                   + scanner.nextShort(12));
            }

            // if no short is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found short value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**Output:** 

```java
Not found short value :Gfg
Found Short value :9
Not found short value :+
Found Short value :6
Not found short value :=
Not found short value :12.0

```

**程序 3:** 演示 InputMismatchException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// nextShort() method of Scanner class in Java
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

                // if the next is a short,
                // print found and the short
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next Short value :"
                                   + scanner.nextShort());
            }
            scanner.close();
        }
        catch (Exception e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:** 

```java
Exception thrown: java.util.InputMismatchException

```

**程序 4:** 演示 NoSuchElementException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// nextShort() method of Scanner class in Java
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

            // Trying to get the next short value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a short,
                // print found and the short
                if (scanner.hasNextShort()) {
                    System.out.println("Found Short value :"
                                       + scanner.nextShort());
                }

                // if no short is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found short value :"
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

**Output:** 

```java
Not found short value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 5:** 演示非法状态异常

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// nextShort() method of Scanner class in Java
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
                               + "next Short value");

            while (scanner.hasNext()) {

                // if the next is a short,
                // print found and the short
                if (scanner.hasNextShort()) {
                    System.out.println("Found Short value :"
                                       + scanner.nextShort());
                }

                // if no short is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found short value :"
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

**Output:** 

```java
Scanner Closed
Trying to get next Short value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextShort()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextShort())
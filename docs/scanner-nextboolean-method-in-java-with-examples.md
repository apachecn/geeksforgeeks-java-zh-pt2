# Java 中 Scanner nextBoolean()方法，示例

> 原文:[https://www . geesforgeks . org/scanner-next boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/scanner-nextboolean-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextBoolean()** 方法将输入的下一个标记作为布尔值进行扫描。如果翻译成功，扫描仪将通过匹配的输入。

**语法:**

```java
public boolean nextBoolean()
```

**参数:**函数不接受任何参数。

**返回值:**该函数从输入中返回**布尔扫描的**。

**异常:**该函数抛出如下三个异常:

*   [T0】 inputismatexception: 【T1] If the next token is not a valid Boolean value
*   Then **nosuchelementException is thrown:** If the input is exhausted, it is thrown.
*   [T0】 illegalstatexception: 【T1] Thrown if this scanner is closed.

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextBoolean() method of Scanner class in Java
// without parameter

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "Gfg true 9 + 6 = 12.0 false";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        while (scanner.hasNext()) {

            // if the next is a Boolean,
            // print found and the Boolean
            if (scanner.hasNextBoolean()) {
                System.out.println("Found Boolean value :"
                                   + scanner.nextBoolean());
            }

            // if no Boolean is foucnd,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found Boolean() value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Boolean() value :Gfg
Found Boolean value :true
Not found Boolean() value :9
Not found Boolean() value :+
Not found Boolean() value :6
Not found Boolean() value :=
Not found Boolean() value :12.0
Found Boolean value :false

```

**程序 2:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextBoolean() method of Scanner class in Java
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

                // if the next is a Boolean
                // print found and the Boolean
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next Boolean value :"
                                   + scanner.nextBoolean());
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
// nextBoolean() method of Scanner class in Java
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

            // Trying to get the next Boolean value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a Boolean,
                // print found and the Boolean
                if (scanner.hasNextBoolean()) {
                    System.out.println("Found Boolean value :"
                                       + scanner.nextBoolean());
                }

                // if no Boolean is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Boolean value :"
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
Not found Boolean value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 4:** 演示非法状态异常

```java
// Java program to illustrate the
// nextBoolean() method of Scanner class in Java
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
                               + "next Boolean value");

            while (scanner.hasNext()) {

                // if the next is a Boolean,
                // print found and the Boolean
                if (scanner.hasNextBoolean()) {
                    System.out.println("Found Boolean value :"
                                       + scanner.nextBoolean());
                }

                // if no Boolean is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Boolean value :"
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
Trying to get next Boolean value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextBoolean()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextBoolean())
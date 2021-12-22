# Java 中 Scanner nextByte()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next byte-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-nextbyte-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextByte(基数)**方法将输入的下一个标记作为字节进行扫描。如果翻译成功，扫描仪将通过匹配的输入。如果参数基数没有被传递，那么它的行为类似于 nextByte(基数)，其中基数被假定为默认基数。

**语法:**

```java
public byte nextByte()
```

**参数:**该函数接受一个参数**基数**，该参数用于将令牌字节化为字节值。

**返回值:**该功能从输入返回**字节扫描的**。

**异常:**函数抛出如下三个异常:

*   [T0】 inputismatexception: 【T1] If the next tag does not match the Byteeger regular expression or is out of range.
*   [T0】 NoSuchElementException: 【T1] Thrown if the input is exhausted.
*   [T0】 illegalstatexception: 【T1] Thrown if this scanner is closed.

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextByte() method of Scanner class in Java
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

            // if the next is a Byte,
            // prByte found and the Byte
            if (scanner.hasNextByte()) {
                System.out.println("Found Byte value :"
                                   + scanner.nextByte());
            }

            // if no Byte is found,
            // prByte "Not Found:" and the token
            else {
                System.out.println("Not found Byte value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Byte value :Gfg
Found Byte value :9
Not found Byte value :+
Found Byte value :6
Not found Byte value :=
Not found Byte value :12.0

```

**程序二:**

```java
// Java program to illustrate the
// nextByte() method of Scanner class in Java
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

            // if the next is a Byte,
            // prByte found and the Byte
            if (scanner.hasNextByte()) {
                System.out.println("Found Byte value :"
                                   + scanner.nextByte(12));
            }

            // if no Byte is found,
            // prByte "Not Found:" and the token
            else {
                System.out.println("Not found Byte value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Byte value :Gfg
Found Byte value :9
Not found Byte value :+
Found Byte value :6
Not found Byte value :=
Not found Byte value :12.0

```

**程序 3:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextByte() method of Scanner class in Java
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

                // if the next is a Byte,
                // prByte found and the Byte
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next Byte value :"
                                   + scanner.nextByte());
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
// nextByte() method of Scanner class in Java
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

            // Trying to get the next Byte value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a Byte,
                // prByte found and the Byte
                if (scanner.hasNextByte()) {
                    System.out.println("Found Byte value :"
                                       + scanner.nextByte());
                }

                // if no Byte is found,
                // prByte "Not Found:" and the token
                else {
                    System.out.println("Not found Byte value :"
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
Not found Byte value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 5:** 演示非法状态异常

```java
// Java program to illustrate the
// nextByte() method of Scanner class in Java
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
                               + "next Byte value");

            while (scanner.hasNext()) {

                // if the next is a Byte,
                // prByte found and the Byte
                if (scanner.hasNextByte()) {
                    System.out.println("Found Byte value :"
                                       + scanner.nextByte());
                }

                // if no Byte is found,
                // prByte "Not Found:" and the token
                else {
                    System.out.println("Not found Byte value :"
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
Trying to get next Byte value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextByte()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextByte())
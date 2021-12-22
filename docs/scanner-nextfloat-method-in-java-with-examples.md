# Java 中 Scanner nextFloat()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next float-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-nextfloat-method-in-java-with-examples/)

类的 **nextFloat()** 方法将输入的下一个标记作为 Float()进行扫描。如果翻译成功，扫描仪将通过匹配的输入。

**语法:**

```java
public float nextFloat()
```

**参数:**函数不接受任何参数。

**返回值:**该功能从输入返回**扫描的**浮点数。

**异常:**如果下一个标记与 Float 正则表达式不匹配，或者超出范围

*   **无搜索项异常:**哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟*   [T0】 illegalstatexception: 【T1] If this scanner is turned off

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextFloat() method of Scanner class in Java
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

            // if the next is a Float,
            // print found and the Float
            if (scanner.hasNextFloat()) {
                System.out.println("Found Float value :"
                                   + scanner.nextFloat());
            }

            // if no float is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found Float() value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found Float() value :Gfg
Found Float value :9.0
Not found Float() value :+
Found Float value :6.0
Not found Float() value :=
Found Float value :12.0

```

**程序 2:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextFloat() method of Scanner class in Java
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

                // if the next is a Float
                // print found and the Float
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next Float value :"
                                   + scanner.nextFloat());
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
// nextFloat() method of Scanner class in Java
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

            // Trying to get the next Float value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a Float,
                // print found and the Float
                if (scanner.hasNextFloat()) {
                    System.out.println("Found Float value :"
                                       + scanner.nextFloat());
                }

                // if no Float is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Float value :"
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
Not found Float value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 4:** 演示非法状态异常

```java
// Java program to illustrate the
// nextFloat() method of Scanner class in Java
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
                               + "next Float value");

            while (scanner.hasNext()) {

                // if the next is a Float,
                // print found and the Float
                if (scanner.hasNextFloat()) {
                    System.out.println("Found Float value :"
                                       + scanner.nextFloat());
                }

                // if no Float is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found Float value :"
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
Trying to get next Float value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextFloat()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextFloat())
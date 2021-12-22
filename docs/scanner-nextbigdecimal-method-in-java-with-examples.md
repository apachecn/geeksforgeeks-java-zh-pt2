# Java 中 Scanner nextBigDecimal()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-next bigdecimal-in-Java-method-with-examples/](https://www.geeksforgeeks.org/scanner-nextbigdecimal-method-in-java-with-examples/)

**[Java . util . scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **nextBigDecimal()** 方法将输入的下一个标记作为 BigDecimal 进行扫描。如果下一个标记与上面定义的十进制正则表达式匹配，那么该标记将被转换为一个大十进制值，就像通过删除所有组分隔符，通过字符数字将非 ASCII 数字映射为 ASCII 数字，并将结果字符串传递给大十进制(字符串)构造函数一样。

**语法:**

```java
public BigDecimal nextBigDecimal()
```

**参数:**函数不接受任何参数。

**返回值:**此功能从输入返回**大十进制扫描的**。

**异常:**该函数抛出如下三个异常:

*   [T0】 inputismatexception: 【T1] If the next tag is not a valid BigDecimal or out of range
*   [T0】 NoSuchElementException: 【T1] Thrown if the input is exhausted.
*   [T0】 illegalstatexception: 【T1] Thrown if this scanner is closed.

以下程序说明了上述功能:

**程序 1:**

```java
// Java program to illustrate the
// nextBigDecimal() method of Scanner class in Java
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

            // if the next is a BigDecimal,
            // print found and the BigDecimal
            if (scanner.hasNextBigDecimal()) {
                System.out.println("Found BigDecimal value :"
                                   + scanner.nextBigDecimal());
            }

            // if no BigDecimal is found,
            // print "Not Found:" and the token
            else {
                System.out.println("Not found BigDecimal() value :"
                                   + scanner.next());
            }
        }
        scanner.close();
    }
}
```

**输出:**

```java
Not found BigDecimal() value :Gfg
Found BigDecimal value :9
Not found BigDecimal() value :+
Found BigDecimal value :6
Not found BigDecimal() value :=
Found BigDecimal value :12.0

```

**程序 2:** 演示输入 ismatcheexception

```java
// Java program to illustrate the
// nextBigDecimal() method of Scanner class in Java
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

                // if the next is a BigDecimal
                // print found and the BigDecimal
                // since the value 60 is out of range
                // it throws an exception

                System.out.println("Next BigDecimal value :"
                                   + scanner.nextBigDecimal());
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
// nextBigDecimal() method of Scanner class in Java
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

            // Trying to get the next BigDecimal value
            // more times than the scanner
            // Hence it will throw exception
            for (int i = 0; i < 5; i++) {

                // if the next is a BigDecimal,
                // print found and the BigDecimal
                if (scanner.hasNextBigDecimal()) {
                    System.out.println("Found BigDecimal value :"
                                       + scanner.nextBigDecimal());
                }

                // if no BigDecimal is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found BigDecimal value :"
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
Not found BigDecimal value :Gfg
Exception thrown: java.util.NoSuchElementException

```

**程序 4:** 演示非法状态异常

```java
// Java program to illustrate the
// nextBigDecimal() method of Scanner class in Java
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
                               + "next BigDecimal value");

            while (scanner.hasNext()) {

                // if the next is a BigDecimal,
                // print found and the BigDecimal
                if (scanner.hasNextBigDecimal()) {
                    System.out.println("Found BigDecimal value :"
                                       + scanner.nextBigDecimal());
                }

                // if no BigDecimal is found,
                // print "Not Found:" and the token
                else {
                    System.out.println("Not found BigDecimal value :"
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
Trying to get next BigDecimal value
Exception thrown: java.lang.IllegalStateException: Scanner closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # nextBigDecimal()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#nextBigDecimal())
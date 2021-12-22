# Java 中的短短值()方法

> 原文:[https://www . geesforgeks . org/short-short value-in-Java-method/](https://www.geeksforgeeks.org/short-shortvalue-method-in-java/)

shortValue()是 Java 中 Short 类的一个内置方法，用于返回*这个*值的 Short 值。

**语法:**

```java
public short shortValue()

```

**参数**:该方法不取任何参数。

**返回值:**方法返回转换为 short 类型后该对象表示的数值。

下面的程序说明了 Short.shortValue()方法:

**程序 1:**

```java
// Java program that demonstrates
// Short.shortValue() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        short svalue = 21;
        Short sh_obj = new Short(svalue);

        // It will return the short value of Short
        short sh_Value = sh_obj.shortValue();

        // Printing short value
        System.out.println("The short value of the given Short is = "
                                                          + sh_Value);
    }
}
```

**Output:**

```java
The short value of the given Short is = 21

```

**程序 2:**

```java
// java program that demonstrates
// Short.shortValue() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        short svalue = -19;
        Short sh_obj = new Short(svalue);

        // It will return the short value of Short
        short sh_Value = sh_obj.shortValue();

        // Printing short value
        System.out.println("The short value of the given Short is = " 
                                                          + sh_Value);
    }
}
```

**Output:**

```java
The short value of the given Short is = -19

```

**程序 3:**
**注意:**当一个十进制值和字符串作为参数传递时，它会返回一条错误消息。

```java
// Java program that demonstrates
// Short.shortValue() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        short svalue = 9.6;
        Short sh_obj = new Short(svalue);

        // It will return the short value of Short
        short sh_Value = sh_obj.shortValue();

        // Printing short value
        System.out.println("The short value of the given Short is = "
        + sh_Value);
        short svalue2 = "61";
        Short sh_obj2 = new Short(svalue2);

        // It will return the short value of Short
        short sh_Value2 = sh_obj2.shortValue();

        // Printing short value
        System.out.println("The short value of the given Short is = " +
        sh_Value2);
    }
}
```

**输出:**

```java

prog.java:10: error: incompatible types: possible lossy conversion from double to short
    short svalue = 9.6;
                   ^
prog.java:18: error: incompatible types: String cannot be converted to short
    short svalue2 = "61";
                    ^
2 errors

```
# Java 中的短反转字节()，示例

> 原文:[https://www . geesforgeks . org/short-reverse bytes-in-Java-with-examples/](https://www.geeksforgeeks.org/short-reversebytes-in-java-with-examples/)

[Short](https://www.geeksforgeeks.org/java-lang-short-class-java/)类的 **reverseBytes()** 方法是 Java 中的内置方法，用于返回通过反转指定短值的二进制补码表示中的字节顺序而获得的值。

**语法:**

```java
public static short reverseBytes(*short a*)
```

**参数:**该方法取一个短类型的参数 *a* ，其字节将被反转。

**返回值:**该方法将返回通过反转指定短值中的字节获得的值。

**示例:**

```java
Input: 75
Output: 1258291200
Explanation:
Consider an short a = 75 
Binary Representation = 1001011
Number of one bit = 4 
After reversing the bytes = 1258291200

Input: -43
Output: -704643073

```

下面的程序说明了 Short.reverseBytes()方法:

**程序 1:** 为正数。

```java
// Java program to illustrate the
// Short.reverseBytes() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // Create a Short instance
        short a = 61;

        // Print the value before reversal of Bytes
        System.out.println("Original value = " + a);

        // Reverse the bytes in the specified short value
        // Using reverseBytes() method
        System.out.println("After reversing the bytes :  \n"
                           + "New value : "
                           + Short.reverseBytes(a));
    }
}
```

**Output:**

```java
Original value = 61
After reversing the bytes :  
New value : 15616

```

**程序 2:** 为负数。

```java
// Java program to illustrate the
// Short.reverseBytes() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // Create a Short instance
        short a = -45;

        // Print the value before reversal of Bytes
        System.out.println("Original value = " + a);

        // Reverse the bytes in the specified short value
        // Using reverseBytes() method
        System.out.println("After reversing the bytes :  \n"
                           + "New value : "
                           + Short.reverseBytes(a));
    }
}
```

**Output:**

```java
Original value = -45
After reversing the bytes :  
New value : -11265

```
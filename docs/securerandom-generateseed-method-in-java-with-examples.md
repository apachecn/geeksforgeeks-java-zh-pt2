# Java 中的 SecureRandom generateSeed()方法，示例

> 原文:[https://www . geeksforgeeks . org/secureandom-generated-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-generateseed-method-in-java-with-examples/)

**Java . security . secureandom**类的 **generateSeed()** 方法用于返回给定的种子字节数，该字节数是使用该类用来给自身播种的种子生成算法计算的。此调用可用于播种其他随机数生成器。

**语法:**

```java
public byte[] generateSeed(int numBytes)
```

**参数:**该方法以**要生成的种子字节数**为参数。

**返回值:**该方法返回**生成的种子字节。**

以下是说明*generate seeded()*方法的示例:

**注意:**

1.  This program will not run on the online IDE.
2.  Every security random class will produce random output.

**例 1:**

## 爪哇

```java
// Java program to demonstrate
// generateSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the generated seed by into byte array
            // by using method generateSeed()
            byte[] arr = sr.generateSeed(8);

            // printing the byte array
            System.out.println(Arrays.toString(arr));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
[24, -16, -12, 25, -3, 66, -90, 103]
```

**例 2:**

## 爪哇

```java
// Java program to demonstrate
// generateSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of SecureRandom getting the instance of TAJMAHAL
            System.out.println("Trying to get the instance from an unknown source");
            SecureRandom sr = SecureRandom.getInstance("TAJMAHAL");

            // getting the generated seed by into byte array
            // by using method generateSeed()
            byte[] arr = sr.generateSeed(5);

            // printing the byte array
            System.out.println("Seed Bytes: " + Arrays.toString(arr));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Trying to get the instance from an unknown source
Exception thrown : java.security.NoSuchAlgorithmException: TAJMAHAL SecureRandom not available
```
# Java 中的 SecureRandom getAlgorithm()方法，带示例

> 原文:[https://www . geesforgeks . org/secureandom-getalgorithm-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-getalgorithm-method-in-java-with-examples/)

**Java . security . SecureRandom**类的 **getAlgorithm()** 方法用于返回这个 secureandom 对象实现的算法的名称。
**语法:**

```java
public String getAlgorithm()
```

**返回值:**该方法返回算法名称，如果无法确定算法名称，则返回未知。
以下是举例说明 *getAlgorithm()* 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Algorithm
            // by using method getAlgorithm()
            String algo = sr.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm: " + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Algorithm: SHA1PRNG
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("TAJMAHAL");

            // getting the Algorithm
            // by using method getAlgorithm()
            String algo = sr.getAlgorithm();

            // printing the string algo
            System.out.println(algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Exception thrown : java.security.NoSuchAlgorithmException: TAJMAHAL SecureRandom not available
```
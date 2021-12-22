# Java 中的提供程序 toString()方法，示例

> 原文:[https://www . geesforgeks . org/provider-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-tostring-method-in-java-with-examples/)

**java.security.Provider** 类的 **toString()** 方法用于返回一个带有该提供程序名称和版本号的字符串。

**语法:**

```java
public String toString()
```

**返回值:**这个方法返回这个提供者的带有**名称和版本号**的字符串。

以下是说明 **toString()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getVersion() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {
            // creating the object of  KeyPairGenerator
            KeyPairGenerator sr = KeyPairGenerator.getInstance("DSA", "SUN");

            // getting the Provider of the KeyPairGenerator sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the name and version of the provider
            // using toString() method
            String nv = provider.toString();

            // printing the string info
            System.out.println("Provider : " + nv);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Provider : SUN version 1.8

```

**例 2:**

```java
// Java program to demonstrate
// getVersion() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {
            // creating the object of  SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the name and version of the provider
            // using toString() method
            String nv = provider.toString();

            // printing the string info
            System.out.println("Provider : " + nv);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Provider : SUN version 1.8

```
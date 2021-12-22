# Java 中的提供者 getVersion()方法，示例

> 原文:[https://www . geesforgeks . org/provider-get version-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-getversion-method-in-java-with-examples/)

**java.security.Provider** 类的 **getVersion()** 方法用于返回该提供程序的版本号

**语法:**

```
public double getVersion()
```

**返回值:**这个方法返回这个提供者的**版本号。**

以下是说明 *getVersion()* 方法的例子:

**例 1:**

```
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

            // getting the version of the provider using getVersion() method
            double version = provider.getVersion();

            // printing the string info
            System.out.println("version : " + version);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
version : 1.8

```

**例 2:**

```
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

            // getting the version of the provider using getVersion() method
            double version = provider.getVersion();

            // printing the string info
            System.out.println("version : " + version);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
version : 1.8

```
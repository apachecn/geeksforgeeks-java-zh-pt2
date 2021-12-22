# Java 中的提供者 getName()方法，示例

> 原文:[https://www . geesforgeks . org/provider-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-getname-method-in-java-with-examples/)

**java.security.Provider** 类的 **getName()** 方法用于返回该提供程序的名称。

**语法:**

```
public String getName()
```

**返回值:**这个方法返回这个提供者的**名字。**

以下是说明 **getName()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// get() method

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

            // getting the name of the provider using getName()
            String name = provider.getName();

            // printing the string info
            System.out.println("name : " + name);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
name : SUN

```

**例 2:**

```
// Java program to demonstrate
// get() method

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

            // getting the name of the provider using getName()
            String name = provider.getName();

            // printing the string info
            System.out.println("name : " + name);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
name : SUN

```
# Java 中的 SecureRandom getProvider()方法，带示例

> 原文:[https://www . geesforgeks . org/secureandom-get provider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-getprovider-method-in-java-with-examples/)

类的 **getProvider()** 方法用于返回这个安全对象的提供者。

**语法:**

```
public final Provider getProvider()
```

**返回值:**这个方法返回这个 SecureRandom 对象的提供者。

以下是说明 *getProvider()* 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getProvider() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the provider name
            System.out.println("Provider name : " + provider.getName());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Provider name : SUN

```

**例 2:**

```
// Java program to demonstrate
// getProvider() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom srand = new SecureRandom(new byte[] { 1, 2, 3, 4 });

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = srand.getProvider();

            // printing the provider name
            System.out.println("Provider name : " + provider.getName());
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Provider name : SUN
```
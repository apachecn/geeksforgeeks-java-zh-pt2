# 提供者。Java 中的 Service getProvider()方法，示例

> 原文:[https://www . geesforgeks . org/provider-service-getprovider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-service-getprovider-method-in-java-with-examples/)

**Java . security . provider . service**类的 **getProvider()** 方法用于返回这个提供者服务对象的提供者。

**语法:**

```
public final Provider getProvider()
```

**返回值:**该方法返回该提供商服务对象的**提供商**。

以下是说明 getProvider()方法的示例:

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

            // creating the object of Signature
            Signature sr
                = Signature.getInstance(
                    "SHA1withDSA", "SUN");

            // getting the Provider of the Signature sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the service of the provider
            // using getServices() method
            Provider.Service service
                = provider
                      .getService("Signature",
                                  sr.getAlgorithm());

            // getting Provider of Provider.Service object
            // by using getProvider() method
            Provider name = service.getProvider();

            // display the result
            System.out.println("Provider : " + name);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
        catch (NoSuchProviderException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Provider : SUN version 1.8

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

            // creating object of MessageDigest
            MessageDigest msd
                = MessageDigest.getInstance("MD5");

            // getting the Provider of the Signature sr
            // by using method getProvider()
            Provider provider = msd.getProvider();

            // getting the service of the provider
            // using getServices() method
            Provider.Service service
                = provider
                      .getService("MessageDigest",
                                  msd.getAlgorithm());

            // getting Provider of Provider.Service object
            // by using getProvider() method
            Provider name = service.getProvider();

            // display the result
            System.out.println("Provider : " + name);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出:**

```
Provider : SUN version 1.8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/Provider。service . html # GetProvider–](https://docs.oracle.com/javase/9/docs/api/java/security/Provider.Service.html#getProvider--)
# 提供者。Java 中的服务 getClassName()方法，示例

> 原文:[https://www . geesforgeks . org/provider-service-getclass name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-service-getclassname-method-in-java-with-examples/)

**Java . security . provider . service**类的 **getClassName()** 方法用于返回利用其提供者服务的类的指定名称。

**语法:**

```
public final String getClassName()
```

**返回值:**该方法返回指定的**类名**。

以下是说明 **getClassName()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getClassName() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr
                = Signature.getInstance(
                    "SHA1withDSA",
                    "SUN");

            // getting the Provider of the Signature sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the service of the provider
            // using getServices() method
            Provider.Service service
                = provider
                      .getService("Signature",
                                  sr.getAlgorithm());

            // getting class name of Provider.Service object
            // by using getClassName() method
            String name = service.getClassName();

            // display the result
            System.out.println("Name of the class : "
                               + name);
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
Name of the class : sun.security.provider.DSA$SHA1withDSA

```

**例 2:**

```
// Java program to demonstrate
// getClassName() method

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

            // getting class name of Provider.Service object
            // by using getClassName() method
            String name = service.getClassName();

            // display the result
            System.out.println("Name of the class : "
                               + name);
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
Name of the class : sun.security.provider.MD5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/Provider。service . html # GetClassName–](https://docs.oracle.com/javase/9/docs/api/java/security/Provider.Service.html#getClassName--)
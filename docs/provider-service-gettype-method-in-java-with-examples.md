# 提供者。Java 中的 Service getType()方法，示例

> 原文:[https://www . geesforgeks . org/provider-service-gettype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-service-gettype-method-in-java-with-examples/)

**Java . security . provider . service**类的 **getType()** 方法提供了提供者服务的类型。

**语法:**

```java
public final String getType()
```

**返回值:**该方法提供特定类型的提供者服务。

以下是说明 **getType()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getType() method

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

            // getting type of Provider.Service object
            // by using getClassName() method
            String name = service.getType();

            // display the result
            System.out.println("Name of the type : "
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

```java
Name of the type : Signature

```

**例 2:**

```java
// Java program to demonstrate
// getType() method

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

            // getting type of Provider.Service object
            // by using getClassName() method
            String name = service.getType();

            // display the result
            System.out.println("Name of the type : "
                               + name);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Name of the type : MessageDigest

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/Provider。service . html # GetType–](https://docs.oracle.com/javase/9/docs/api/java/security/Provider.Service.html#getType--)
# 提供者。Java 中的服务 toString()方法，示例

> 原文:[https://www . geesforgeks . org/provider-service-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-service-tostring-method-in-java-with-examples/)

**Java . security . provider . service**类的 **toString()** 方法返回该提供者服务的字符串表示形式。

**语法:**

```
public String toString()
```

**返回值:**这个方法提供了这个提供者服务的字符串表示。

以下是说明 **toString()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// toString() method

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

            // getting string representation
            // of Provider.Service object
            // by using getClassName() method
            String value = service.toString();

            // display the result
            System.out.println("String representation : "
                               + value);
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

**Output:**

> 字符串表示:SUN:签名。sha1 withsa-> sun . security . provider . DSA $ sha1 withsa
> 别名:【DSA、DSS、SHA/DSA、SHA-1/DSA、SHA1/DSA、SHAwithDSA、DSAWithSHA1、OID.1.2.840.10040.4.3、1.2.840.10040.4.3、1.3.14.3.2.13、1 . 3 . 14 . 3 . 2 . 27】
> 属性:{ ImplementedIn

**例 2:**

```
// Java program to demonstrate
// toString() method

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

            // getting a string representation
            // of Provider.Service object
            // by using getClassName() method
            String value = service.toString();

            // display the result
            System.out.println("String representation : "
                               + value);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

> 字符串表示:SUN: MessageDigest。MD5-> sun . security . provider . MD5
> 属性:{ImplementedIn=Software}

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/Provider。service . html # ToString–](https://docs.oracle.com/javase/9/docs/api/java/security/Provider.Service.html#toString--)
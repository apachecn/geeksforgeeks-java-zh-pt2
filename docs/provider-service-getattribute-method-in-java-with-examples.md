# 提供者。Java 中的 Service getAttribute()方法，示例

> 原文:[https://www . geesforgeks . org/provider-service-getattribute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-service-getattribute-method-in-java-with-examples/)

**Java . security . provider . service**类的 **getAttribute()** 方法用于返回该方法中传递的特定属性名的属性值。

**语法:**

```java
public final String getAttribute(String name)
```

**返回值:**该方法返回特定属性类型的**值**。

以下是说明 **getAttribute()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getAttribute() method

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

            // getting algorithm of Provider.Service object
            // by using getAlgorithm() method
            String algo = service.getAttribute("KeySize");

            // display the result
            System.out.println("KeySize is : " + algo);
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
KeySize is : 1024

```

**例 2:**

```java
// Java program to demonstrate
// getAttribute() method

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

            // getting algorithm of Provider.Service object
            // by using getAlgorithm() method
            String algo
                = service.getAttribute("ImplementedIn");

            // display the result
            System.out.println("ImplementedIn : "
                               + algo);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出:**

```java
ImplementedIn : Software

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/Provider。service . html # GetAttribute-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/security/Provider.Service.html#getAttribute-java.lang.String-)
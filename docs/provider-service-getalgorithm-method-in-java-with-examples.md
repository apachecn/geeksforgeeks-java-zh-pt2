# 提供者。Java 中的服务 getAlgorithm()方法，示例

> 原文:[https://www . geesforgeks . org/provider-service-getalgorithm-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-service-getalgorithm-method-in-java-with-examples/)

**Java . security . Provider . service**类的 **getAlgorithm()** 方法用于返回此 Provider 的算法的标准名称。服务与关联。

**语法:**

```
public final String getAlgorithm()
```

**返回值:**该方法返回**算法名称**。

以下是说明 **getAlgorithm()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAlgorithm() method

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
            Provider provider
                = sr.getProvider();

            // getting the service of the provider
            // using getServices() method
            Provider.Service service
                = provider
                      .getService("Signature",
                                  sr.getAlgorithm());

            // getting algorithm of Provider.Service object
            // by using getAlgorithm() method
            String algo = service.getAlgorithm();

            // display the result
            System.out.println("Algorithm : " + algo);
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

```
Algorithm : SHA1withDSA
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAlgorithm() method

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
            String algo = service.getAlgorithm();

            // display the result
            System.out.println("Algorithm : " + algo);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Algorithm : MD5
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/Provider。service . html # getAlgorithm–](https://docs.oracle.com/javase/9/docs/api/java/security/Provider.Service.html#getAlgorithm--)
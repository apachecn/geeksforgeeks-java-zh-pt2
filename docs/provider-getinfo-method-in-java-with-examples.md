# Java 中的提供者 getInfo()方法，示例

> 原文:[https://www . geesforgeks . org/provider-getinfo-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-getinfo-method-in-java-with-examples/)

**java.security.Provider** 类的 **getInfo()** 方法用于返回提供者及其服务的人类可读描述。这可能会返回一个带有相关链接的网页。

**语法:**

```
public String getInfo()
```

**返回值:**该方法返回提供者及其服务的**描述**。

以下是说明 *getInfo()* 方法的例子:

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

            // getting the info
            String info = provider.getInfo();

            // printing the string info
            System.out.println("info : " + info);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
info : 
SUN (DSA key/parameter generation;
    DSA signing; SHA-1, MD5 digests; 
    SecureRandom; X.509 certificates; 
    JKS & DKS keystores; 
    PKIX CertPathValidator; 
    PKIX CertPathBuilder; 
    LDAP, Collection CertStores, JavaPolicy Policy; 
    JavaLoginConfig Configuration)

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

            // getting the info
            String info = provider.getInfo();

            // printing the string info
            System.out.println("info : " + info);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
info : 
SUN (DSA key/parameter generation; 
    DSA signing; SHA-1, MD5 digests; 
    SecureRandom; X.509 certificates; 
    JKS & DKS keystores; 
    PKIX CertPathValidator; 
    PKIX CertPathBuilder; 
    LDAP, Collection CertStores, JavaPolicy Policy; 
    JavaLoginConfig Configuration)

```
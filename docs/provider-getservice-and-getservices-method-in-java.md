# Java 中的提供者 getService()和 getServices()方法

> 原文:[https://www . geesforgeks . org/provider-get service-and-get services-method-in-Java/](https://www.geeksforgeeks.org/provider-getservice-and-getservices-method-in-java/)

### 获取服务(字符串类型，字符串算法)

**java.security.Provider** 类的 **getService()** 方法用于获取描述该提供者对该算法或别名的指定类型的实现的服务。

如果不存在这样的实现，此方法返回 null。如果有两个匹配的服务，一个使用 putService()添加到此提供程序，另一个通过 put()添加，则返回通过 putService()添加的服务。

**语法:**

```
public Provider.Service getService(String type, String algorithm)
```

**参数:**该方法将以下参数作为参数。

*   **类型**–请求的服务类型。
*   **算法**–所请求服务的不区分大小写的算法名称(或替代别名)。

**返回值:**该方法返回描述该提供商匹配服务的**服务**，如果不存在该服务，则返回**空值**。

**异常:**如果类型或算法为空，该方法抛出**空指针异常**。

以下是说明 *getService()* 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getService() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {
            // creating the object of  SecureRandom
            Signature sr = Signature.getInstance("SHA1withDSA", "SUN");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the service of the provider using getServices() method
            Provider.Service service1 = provider
                                            .getService("Signature", sr.getAlgorithm());

            // printing the service
            System.out.println("Provider service : " + service1);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Provider service : SUN: Signature.SHA1withDSA -> sun.security.provider.DSA$SHA1withDSA
  aliases: [DSA, DSS, SHA/DSA, SHA-1/DSA, SHA1/DSA, SHAwithDSA, DSAWithSHA1, OID.1.2.840.10040.4.3, 1.2.840.10040.4.3, 1.3.14.3.2.13, 1.3.14.3.2.27]
  attributes: {ImplementedIn=Software, KeySize=1024, SupportedKeyClasses=java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey}

```

**示例 2:** 展示 getService()方法抛出的 NullPointerException。

```
// Java program to demonstrate
// getService() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {
            // creating the object of  SecureRandom
            Signature sr = Signature.getInstance("SHA1withDSA", "SUN");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the service of the provider using getServices() method
            Provider.Service service1 = provider
                                            .getService(null, sr.getAlgorithm());

            // printing the service
            System.out.println("Provider service : " + service1);
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Exception thrown : java.lang.NullPointerException

```

### getServices()

**java.security.Provider** 类的 **getServices()** 方法用于获取该提供程序支持的所有服务的不可修改集合。

**语法:**

```
public Set<Provider.Service> getServices()
```

**返回值:**该方法返回一个由该提供商支持的所有服务的**不可修改集**。

以下是说明 getServices()方法的示例:

**程序 1:**

```
// Java program to demonstrate
// getService() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        // Declaring int variable
        int i = 5;

        try {
            // creating the object of  SecureRandom
            Signature sr = Signature.getInstance("SHA1withDSA", "SUN");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of set<Map> type
            Set<Provider.Service> servicelist;

            // getting the service of the provider using getServices() method
            servicelist = provider.getServices();

            // Creating the object of iterator to iterate set
            Iterator<Provider.Service> iter = servicelist.iterator();

            // printing the set elements
            System.out.println("Provider servicelist : \n ");
            while (i > 0) {
                System.out.println("Value is : " + iter.next());
                i--;
            }
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Provider servicelist : 

Value is : SUN: SecureRandom.NativePRNG -> sun.security.provider.NativePRNG

Value is : SUN: SecureRandom.SHA1PRNG -> sun.security.provider.SecureRandom
  attributes: {ImplementedIn=Software}

Value is : SUN: SecureRandom.NativePRNGBlocking -> sun.security.provider.NativePRNG$Blocking

Value is : SUN: SecureRandom.NativePRNGNonBlocking -> sun.security.provider.NativePRNG$NonBlocking

Value is : SUN: Signature.SHA1withDSA -> sun.security.provider.DSA$SHA1withDSA
  aliases: [DSA, DSS, SHA/DSA, SHA-1/DSA, SHA1/DSA, SHAwithDSA, DSAWithSHA1, OID.1.2.840.10040.4.3, 1.2.840.10040.4.3, 1.3.14.3.2.13, 1.3.14.3.2.27]
  attributes: {ImplementedIn=Software, KeySize=1024, SupportedKeyClasses=java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey}

```
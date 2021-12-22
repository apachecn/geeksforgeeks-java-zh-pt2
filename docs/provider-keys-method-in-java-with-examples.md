# Java 中的提供者键()方法，示例

> 原文:[https://www . geesforgeks . org/provider-key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-keys-method-in-java-with-examples/)

**java.security.Provider** 类的**key()**方法用于返回这个哈希表中的键的枚举。

**语法:**

```
public Enumeration keys()
```

**返回值:**这个方法返回这个哈希表中键的一个**枚举。**

以下是说明*键()*方法的示例:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// keys() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        // Declaring int variable
        int i = 10;

        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("NativePRNGBlocking");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of Enumeration<Object> type
            Enumeration<Object> enume;

            // getting the enumeration of the keys
            enume = provider.keys();

            // printing the enumerated keys
            System.out.println("enumeration of the values: \n");
            while (i > 0) {
                System.out.println("Value is: " + enume.nextElement());
                i--;
            }
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
enumeration of the values: 

Value is: Alg.Alias.Signature.SHA1/DSA
Value is: Alg.Alias.Signature.1.2.840.10040.4.3
Value is: Alg.Alias.Signature.DSS
Value is: SecureRandom.SHA1PRNG ImplementedIn
Value is: KeyStore.JKS
Value is: Alg.Alias.MessageDigest.SHA-1
Value is: MessageDigest.SHA
Value is: KeyStore.CaseExactJKS
Value is: CertStore.com.sun.security.IndexedCollection ImplementedIn
Value is: Signature.SHA256withDSA
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// keys() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        // Declaring int variable
        int i = 10;

        try {
            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1withDSA");

            // getting the Provider of the Signature sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of Enumeration<Object> type
            Enumeration<Object> enume;

            // getting the enumeration of the keys
            enume = provider.keys();

            // printing the enumerated keys
            System.out.println("enumeration of the values: \n");
            while (i > 0) {
                System.out.println("Value is: " + enume.nextElement());
                i--;
            }
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
enumeration of the values: 

Value is: Alg.Alias.Signature.SHA1/DSA
Value is: Alg.Alias.Signature.1.2.840.10040.4.3
Value is: Alg.Alias.Signature.DSS
Value is: SecureRandom.SHA1PRNG ImplementedIn
Value is: KeyStore.JKS
Value is: Alg.Alias.MessageDigest.SHA-1
Value is: MessageDigest.SHA
Value is: KeyStore.CaseExactJKS
Value is: CertStore.com.sun.security.IndexedCollection ImplementedIn
Value is: Signature.SHA256withDSA
```
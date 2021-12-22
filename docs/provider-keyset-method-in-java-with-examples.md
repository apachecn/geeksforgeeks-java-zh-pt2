# Java 中的提供者密钥集()方法，示例

> 原文:[https://www . geesforgeks . org/provider-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-keyset-method-in-java-with-examples/)

**java.security.Provider** 类的 **keySet()** 方法用于返回此提供程序中包含的属性键的不可修改的 Set 视图。

**语法:**

```java
public Set keySet()
```

**返回值:**该方法返回包含在该地图中的键的**集合视图。**

以下是说明**键集()**方法的示例:

**程序 1:**

```java
// Java program to demonstrate
// keySet() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        // Declaring int value i
        int i = 10;

        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of set<Map> type
            Set<Object> keyset;

            // getting unmodifiable Set view of the keyset
            keyset = provider.keySet();

            // Creating the object of iterator to iterate set
            Iterator iter = keyset.iterator();

            // printing the set elements
            System.out.println("unmodifiable Set view : \n ");
            while (i > 0) {
                System.out.println("Value is : " + iter.next());
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

```java
unmodifiable Set view : 

Value is : Alg.Alias.Signature.SHA1/DSA
Value is : Alg.Alias.Signature.1.2.840.10040.4.3
Value is : Alg.Alias.Signature.DSS
Value is : SecureRandom.SHA1PRNG ImplementedIn
Value is : KeyStore.JKS
Value is : Alg.Alias.MessageDigest.SHA-1
Value is : MessageDigest.SHA
Value is : KeyStore.CaseExactJKS
Value is : CertStore.com.sun.security.IndexedCollection ImplementedIn
Value is : Signature.SHA256withDSA

```

**程序 2:**

```java
// Java program to demonstrate
// keySet() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        // Declaring int value i
        int i = 10;

        try {
            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1withDSA");

            // getting the Provider of the  Signature sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of set<Map> type
            Set<Object> keyset;

            // getting unmodifiable Set view of the keyset
            keyset = provider.keySet();

            // Creating the object of iterator to iterate set
            Iterator iter = keyset.iterator();

            // printing the set elements
            System.out.println("unmodifiable Set view : \n ");
            while (i > 0) {
                System.out.println("Value is : " + iter.next());
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

```java
unmodifiable Set view : 

Value is : Alg.Alias.Signature.SHA1/DSA
Value is : Alg.Alias.Signature.1.2.840.10040.4.3
Value is : Alg.Alias.Signature.DSS
Value is : SecureRandom.SHA1PRNG ImplementedIn
Value is : KeyStore.JKS
Value is : Alg.Alias.MessageDigest.SHA-1
Value is : MessageDigest.SHA
Value is : KeyStore.CaseExactJKS
Value is : CertStore.com.sun.security.IndexedCollection ImplementedIn
Value is : Signature.SHA256withDSA

```
# Java 中的提供程序元素()方法，示例

> 原文:[https://www . geesforgeks . org/provider-elements-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-elements-method-in-java-with-examples/)

**java.security.Provider** 类的**元素()**方法用于返回给定哈希表中值的枚举。

**语法:**

```java
public Enumeration<Object> elements()
```

**返回值:**该方法返回哈希表中值的**枚举**。

以下是说明*元素()*方法的示例:

**例 1:**

```java
// Java program to demonstrate
// elements() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Provider of the SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the Provider
            System.out.println("Provider of the SHA1PRNG: " + provider);

            // Declaring the variable of Enumeration<Object> type
            Enumeration<Object> enume;

            // getting the enumeration of the values
            enume = provider.elements();

            // printing the enummerated value
            System.out.println("Enumeration of the values: \n");

            while (enume.hasMoreElements()) {
                System.out.println("Value is: " + enume.nextElement());
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
Provider of the SHA1PRNG: SUN version 1.8
Enumeration of the values: 

Value is: SHA1withDSA
Value is: SHA1withDSA
Value is: SHA1withDSA
Value is: Software
Value is: sun.security.provider.JavaKeyStore$DualFormatJKS
Value is: SHA
Value is: sun.security.provider.SHA
Value is: sun.security.provider.JavaKeyStore$CaseExactJKS
Value is: Software
Value is: sun.security.provider.DSA$SHA256withDSA
Value is: SHA
Value is: SHA1withDSA
Value is: Software
Value is: Software
Value is: Software
Value is: sun.security.provider.DSA$RawDSA
Value is: X.509
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.certpath.IndexedCollectionCertStore
Value is: sun.security.provider.Sun
Value is: SHA
Value is: SHA1withDSA
Value is: sun.security.provider.DomainKeyStore$DKS
Value is: Software
Value is: SHA256withDSA
Value is: SHA224withDSA
Value is: 1024
Value is: 1024
Value is: Software
Value is: sun.security.provider.DSAKeyFactory
Value is: sun.security.provider.ConfigFile$Spi
Value is: SHA1withDSA
Value is: SHA-224
Value is: DSA
Value is: Software
Value is: SHA-512
Value is: SHA-384
Value is: SHA-256
Value is: NONEwithDSA
Value is: SUN
Value is: DSA
Value is: RFC3280
Value is: sun.security.provider.PolicySpiFile
Value is: 2048
Value is: DSA
Value is: DSA
Value is: SHA1withDSA
Value is: DSA
Value is: sun.security.provider.SHA5$SHA384
Value is: sun.security.provider.SHA2$SHA224
Value is: Software
Value is: sun.security.provider.DSAParameterGenerator
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.NativePRNG$Blocking
Value is: sun.security.provider.SHA5$SHA512
Value is: DSA
Value is: sun.security.provider.certpath.SunCertPathBuilder
Value is: SHA1withDSA
Value is: SHA-224
Value is: Software
Value is: SHA-512
Value is: 1.8
Value is: SHA-384
Value is: 2048
Value is: SHA-256
Value is: sun.security.provider.DSAParameters
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.certpath.CollectionCertStore
Value is: Software
Value is: sun.security.provider.NativePRNG$NonBlocking
Value is: 2048
Value is: sun.security.provider.certpath.ldap.LDAPCertStore
Value is: sun.security.provider.X509Factory
Value is: SHA256withDSA
Value is: SHA224withDSA
Value is: sun.security.provider.NativePRNG
Value is: RFC2587
Value is: Software
Value is: Software
Value is: RFC3280
Value is: Software
Value is: sun.security.provider.DSA$SHA224withDSA
Value is: SHA1withDSA
Value is: sun.security.provider.certpath.PKIXCertPathValidator
Value is: SHA
Value is: 2048
Value is: sun.security.provider.SecureRandom
Value is: sun.security.provider.DSA$SHA1withDSA
Value is: DSA
Value is: Software
Value is: sun.security.provider.DSAKeyPairGenerator$Current
Value is: SUN (DSA key/parameter generation; DSA signing; SHA-1, MD5 digests; SecureRandom; X.509 certificates; JKS & DKS keystores; PKIX CertPathValidator; PKIX CertPathBuilder; LDAP, Collection CertStores, JavaPolicy Policy; JavaLoginConfig Configuration)
Value is: DSA
Value is: SHA1withDSA
Value is: sun.security.provider.MD5
Value is: SHA1withDSA
Value is: sun.security.provider.SHA2$SHA256
Value is: DSA
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.MD2

```

**例 2:**

```java
// Java program to demonstrate
// elements() method

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

            // printing the Provider
            System.out.println("Provider of the DSA, SUN: " + provider);

            // Declaring the variable of Enumeration<Object> type
            Enumeration<Object> enume;

            // getting the enumeration of the values
            enume = provider.elements();

            // printing the enummerated value
            System.out.println("enumeration of the values: \n");
            while (enume.hasMoreElements()) {
                System.out.println("Value is: " + enume.nextElement());
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
Provider of the DSA, SUN: SUN version 1.8
enumeration of the values: 

Value is: SHA1withDSA
Value is: SHA1withDSA
Value is: SHA1withDSA
Value is: Software
Value is: sun.security.provider.JavaKeyStore$DualFormatJKS
Value is: SHA
Value is: sun.security.provider.SHA
Value is: sun.security.provider.JavaKeyStore$CaseExactJKS
Value is: Software
Value is: sun.security.provider.DSA$SHA256withDSA
Value is: SHA
Value is: SHA1withDSA
Value is: Software
Value is: Software
Value is: Software
Value is: sun.security.provider.DSA$RawDSA
Value is: X.509
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.certpath.IndexedCollectionCertStore
Value is: sun.security.provider.Sun
Value is: SHA
Value is: SHA1withDSA
Value is: sun.security.provider.DomainKeyStore$DKS
Value is: Software
Value is: SHA256withDSA
Value is: SHA224withDSA
Value is: 1024
Value is: 1024
Value is: Software
Value is: sun.security.provider.DSAKeyFactory
Value is: sun.security.provider.ConfigFile$Spi
Value is: SHA1withDSA
Value is: SHA-224
Value is: DSA
Value is: Software
Value is: SHA-512
Value is: SHA-384
Value is: SHA-256
Value is: NONEwithDSA
Value is: SUN
Value is: DSA
Value is: RFC3280
Value is: sun.security.provider.PolicySpiFile
Value is: 2048
Value is: DSA
Value is: DSA
Value is: SHA1withDSA
Value is: DSA
Value is: sun.security.provider.SHA5$SHA384
Value is: sun.security.provider.SHA2$SHA224
Value is: Software
Value is: sun.security.provider.DSAParameterGenerator
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.NativePRNG$Blocking
Value is: sun.security.provider.SHA5$SHA512
Value is: DSA
Value is: sun.security.provider.certpath.SunCertPathBuilder
Value is: SHA1withDSA
Value is: SHA-224
Value is: Software
Value is: SHA-512
Value is: 1.8
Value is: SHA-384
Value is: 2048
Value is: SHA-256
Value is: sun.security.provider.DSAParameters
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.certpath.CollectionCertStore
Value is: Software
Value is: sun.security.provider.NativePRNG$NonBlocking
Value is: 2048
Value is: sun.security.provider.certpath.ldap.LDAPCertStore
Value is: sun.security.provider.X509Factory
Value is: SHA256withDSA
Value is: SHA224withDSA
Value is: sun.security.provider.NativePRNG
Value is: RFC2587
Value is: Software
Value is: Software
Value is: RFC3280
Value is: Software
Value is: sun.security.provider.DSA$SHA224withDSA
Value is: SHA1withDSA
Value is: sun.security.provider.certpath.PKIXCertPathValidator
Value is: SHA
Value is: 2048
Value is: sun.security.provider.SecureRandom
Value is: sun.security.provider.DSA$SHA1withDSA
Value is: DSA
Value is: Software
Value is: sun.security.provider.DSAKeyPairGenerator$Current
Value is: SUN (DSA key/parameter generation; DSA signing; SHA-1, MD5 digests; SecureRandom; X.509 certificates; JKS & DKS keystores; PKIX CertPathValidator; PKIX CertPathBuilder; LDAP, Collection CertStores, JavaPolicy Policy; JavaLoginConfig Configuration)
Value is: DSA
Value is: SHA1withDSA
Value is: sun.security.provider.MD5
Value is: SHA1withDSA
Value is: sun.security.provider.SHA2$SHA256
Value is: DSA
Value is: java.security.interfaces.DSAPublicKey|java.security.interfaces.DSAPrivateKey
Value is: sun.security.provider.MD2

```
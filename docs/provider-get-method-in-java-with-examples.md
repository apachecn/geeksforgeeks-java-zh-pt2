# Java 中的提供程序 get()方法，示例

> 原文:[https://www . geesforgeks . org/provider-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-get-method-in-java-with-examples/)

**java.security.Provider** 类的 **get()** 方法用于返回指定键映射到的值，如果该映射不包含该键的映射，则返回 null。

更正式地说，如果这个映射包含从键 k 到值 v 的映射，使得(key.equals(k))，那么这个方法返回 v；否则返回 null。(这样的映射最多只能有一个。)

**语法:**

```java
public Object get(Object key)
```

**参数:**该方法将**键**作为要返回其关联值的参数。

**返回值:**该方法返回指定键映射到的**值，如果该映射不包含键映射，则返回空值**。

以下是举例说明 *get()* 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// get() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        // Declaring int values
        int i = 10, j = 10;

        try {
            // creating the object of  KeyPairGenerator
            KeyPairGenerator sr = KeyPairGenerator.getInstance("DSA", "SUN");

            // getting the Provider of the KeyPairGenerator sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of set<Map> type
            Set<Object> set;

            // getting unmodifiable Set view of the property entries
            set = provider.keySet();

            // Creating the object of iterator to iterate set
            Iterator iter = set.iterator();

            while (i > 0) {

                // getting the mapped value in element
                // using get() method
                Object element = provider.get(iter.next());

                // printing the mapped value
                System.out.println("value is : " + element);
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
value is : SHA1withDSA
value is : SHA1withDSA
value is : SHA1withDSA
value is : Software
value is : sun.security.provider.JavaKeyStore$DualFormatJKS
value is : SHA
value is : sun.security.provider.SHA
value is : sun.security.provider.JavaKeyStore$CaseExactJKS
value is : Software
value is : sun.security.provider.DSA$SHA256withDSA

```

**例 2:**

```java
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

            // getting the mapped value in element
            // using get() method
            System.out.println("Trying to get the value of an unmapped key");
            Object element = provider.get("geeks");

            // printing the mapped value
            System.out.println("value is : " + element);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Trying to get the value of an unmapped key
value is : null

```
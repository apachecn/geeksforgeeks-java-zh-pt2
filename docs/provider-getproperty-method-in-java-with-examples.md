# Java 中的提供者 getProperty()方法，示例

> 原文:[https://www . geesforgeks . org/provider-getproperty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/provider-getproperty-method-in-java-with-examples/)

**java.security.Provider** 类的 **getProperty()** 方法用于在该属性列表中搜索具有指定关键字的属性。如果在该属性列表中找不到该键，则递归地检查默认属性列表及其默认值。如果找不到属性，方法将返回 null。

**语法:**

```
public String getProperty(String key)
```

**参数:**该方法以**属性键**为参数。

**返回值:**该方法返回该属性列表中带有指定键值的**值，如果没有找到该属性则返回**空值**。**

以下是说明 *getProperty()* 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getProperty() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        // Declaring int values
        int i = 10;

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
                // using getProperty() method
                String property = provider.getProperty((String)iter.next());

                // printing the property of specified key
                System.out.println("value is : " + property);
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

```
// Java program to demonstrate
// getProperty() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        // Declaring int values
        int i = 10;

        try {
            // creating the object of  KeyPairGenerator
            KeyPairGenerator sr = KeyPairGenerator.getInstance("DSA", "SUN");

            // getting the Provider of the KeyPairGenerator sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // getting the mapped value in element
            // using getProperty() method
            System.out.println("Trying to search for unspecified key");
            String property = provider.getProperty("geeks");

            // printing the property of specified key
            System.out.println("value is : " + property);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Trying to search for unspecified key
value is : null

```
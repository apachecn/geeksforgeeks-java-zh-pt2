# Java 中的提供程序值()方法，示例

> 原文:[https://www . geesforgeks . org/provider-values-in-Java-method-with-examples/](https://www.geeksforgeeks.org/provider-values-method-in-java-with-examples/)

**java.security.Provider** 类的 **values()** 方法用于返回此提供程序中包含的属性值的不可修改的集合视图。
**语法:**

```
public Collection<Object> values()
```

**返回值:**此方法返回此地图中包含的值的**集合视图。
以下举例说明*值()*方法:
**例 1:**** 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// values() method

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
            Collection<Object> value;

            // getting unmodifiable Set view of the property value
            value = provider.values();

            // Creating the object of iterator to iterate set
            Iterator iter = value.iterator();

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

```
unmodifiable Set view : 

Value is : SHA1withDSA
Value is : SHA1withDSA
Value is : SHA1withDSA
Value is : Software
Value is : sun.security.provider.JavaKeyStore$DualFormatJKS
Value is : SHA
Value is : sun.security.provider.SHA
Value is : sun.security.provider.JavaKeyStore$CaseExactJKS
Value is : Software
Value is : sun.security.provider.DSA$SHA256withDSA
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// values() method

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

            // getting the Provider of the  SecureRandom sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // Declaring the variable of set<Map> type
            Collection<Object> value;

            // getting unmodifiable Set view of the property value
            value = provider.values();

            // Creating the object of iterator to iterate set
            Iterator iter = value.iterator();

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

```
unmodifiable Set view : 

Value is : SHA1withDSA
Value is : SHA1withDSA
Value is : SHA1withDSA
Value is : Software
Value is : sun.security.provider.JavaKeyStore$DualFormatJKS
Value is : SHA
Value is : sun.security.provider.SHA
Value is : sun.security.provider.JavaKeyStore$CaseExactJKS
Value is : Software
Value is : sun.security.provider.DSA$SHA256withDSA
```
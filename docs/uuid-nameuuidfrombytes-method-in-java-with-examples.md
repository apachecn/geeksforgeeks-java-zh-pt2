# Java 中的 UUID nameUUIDFromBytes()方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-nameuuidfrombytes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-nameuuidfrombytes-method-in-java-with-examples/)

Java 中 **UUID 类**的**nameuidFromBytes()**方法一般用于根据指定的字节数组检索基于 UUID 的第三个类型名。这被用作静态工厂方法。

**语法:**

```
public static UUID nameUUIDFromBytes(byte[] byte_name)
```

**参数:**这个方法接受一个参数 **byte_name** ，这个参数指的是用来构造 UUID 的字节数组。

**返回值:**该方法返回从指定数组生成的 **UUID 实例**。

以下程序说明了 nameUUIDFromBytes()方法的工作原理:

**程序 1:**

```
// Java code to illustrate nameUUIDFromBytes() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating a byte array
        byte[] byte_name
            = { 50, 40, 30, 20, 10 };

        // Printing the byte[]
        System.out.println("Specified byte array: "
                           + Arrays.toString(byte_name));

        // Creating an UUID from byte
        UUID UU_ID
            = UUID
                  .nameUUIDFromBytes(byte_name);

        // Displaying the UUID value
        System.out.println("UUID value from byte: "
                           + UU_ID);
    }
}
```

**Output:**

```
Specified byte array: [50, 40, 30, 20, 10]
UUID value from byte: d66541c4-a9db-3308-8c67-bbf87dc0df8b

```

**程序 2:**

```
// Java code to illustrate nameUUIDFromBytes() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating a byte array
        byte[] byte_name
            = { 10, 15, 1, 45, 13, 20, 71 };

        // Printing the byte[]
        System.out.println("Specified byte array: "
                           + Arrays.toString(byte_name));

        // Creating an UUID from byte
        UUID UU_ID
            = UUID
                  .nameUUIDFromBytes(byte_name);

        // Displaying the UUID value
        System.out.println("UUID value from byte: "
                           + UU_ID);
    }
}
```

**Output:**

```
Specified byte array: [10, 15, 1, 45, 13, 20, 71]
UUID value from byte: 15fe1179-e857-306b-ad67-b2388e006c8a

```
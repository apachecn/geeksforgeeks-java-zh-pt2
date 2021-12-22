# Java 中的 UUID hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-hashcode-method-in-java-with-examples/)

Java 中 **UUID 类**的 **hashCode()** 方法一般用来获取 UUID 的 hash 码值。

**语法:**

```
public int hashCode()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**整数值**，这是这个 UUID 实例的哈希码值。

下面的程序说明了 hashCode()方法的工作原理:

**程序 1:**

```
// Java code to illustrate hashCode() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating two UUIDs
        UUID UUID_1
            = UUID
                  .fromString(
                      "58e0a7d7-eebc-11d8-9669-0800200c9a66");

        // Displaying the UUID
        System.out.println("UUID: "
                           + UUID_1);

        // Displaying the hashCode value
        System.out.println("The hashCode value is: "
                           + UUID_1.hashCode());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The hashCode value is: 3744873

```

**程序 2:**

```
// Java code to illustrate hashCode() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating two UUIDs
        UUID UUID_1
            = UUID
                  .fromString(
                      "5fc03087-d265-11e7-b8c6-83e29cd24f4c");

        // Displaying the UUID
        System.out.println("UUID: "
                           + UUID_1);

        // Displaying the hashCode Value
        System.out.println("The hashCode value is: "
                           + UUID_1.hashCode());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The hashCode value is: -1447957042

```
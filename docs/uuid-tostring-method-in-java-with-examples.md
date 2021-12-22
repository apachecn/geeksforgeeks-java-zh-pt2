# Java 中的 UUID toString()方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-tostring-method-in-java-with-examples/)

Java 中的 **UUID 类**的 **toString()** 方法一般用来获取这个 UUID 的字符串表示。

**语法:**

```
public String toString()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**字符串值**，它是这个 UUID 的字符串表示。

下面的程序说明了 toString()方法的工作原理:

**程序 1:**

```
// Java code to illustrate toString() method

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

        // Displaying the string representation
        System.out.println("The string representation is: "
                           + UUID_1.toString());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The string representation is: 58e0a7d7-eebc-11d8-9669-0800200c9a66

```

**程序 2:**

```
// Java code to illustrate toString() method

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

        // Displaying the toString Value
        System.out.println("The string representation is: "
                           + UUID_1.toString());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The string representation is: 5fc03087-d265-11e7-b8c6-83e29cd24f4c

```
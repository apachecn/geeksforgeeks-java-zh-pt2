# Java 中的 UUID 变体()方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-variant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-variant-method-in-java-with-examples/)

每个 UUID 都有一个不同的数字来描述这个 UUID 的产生。Java 中 **UUID 类**的**变体()**方法一般用来获取与这个 UUID 相关联的变体编号。

**语法:**

```
public int variant()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**整数值**，它是与这个 UUID 相关的变量数。

下面的程序说明了 variant()方法的工作原理:

**程序 1:**

```
// Java code to illustrate variant() method

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

        // Displaying the variant number
        System.out.println("The variant number is: "
                           + UUID_1.variant());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The variant number is: 2

```

**程序 2:**

```
// Java code to illustrate variant() method

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

        // Displaying the variant Value
        System.out.println("The variant number is: "
                           + UUID_1.variant());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The variant number is: 2

```
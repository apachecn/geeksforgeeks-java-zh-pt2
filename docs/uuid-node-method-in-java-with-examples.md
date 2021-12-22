# Java 中的 UUID 节点()方法，示例

> 原文:[https://www . geesforgeks . org/uuid-node-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-node-method-in-java-with-examples/)

Java 中 **UUID 类**的**节点()**方法一般用来获取与这个 UUID 关联的节点值。

**语法:**

```
public long node()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**长值**，它是与这个 UUID 关联的节点值。

**异常:**这个方法抛出**不支持操作异常**如果这个 UUID 不是版本 1 的 UUID

下面的程序说明了 node()方法的工作原理:

**程序 1:**

```
// Java code to illustrate node() method

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

        // Displaying the node value
        System.out.println("The node value is: "
                           + UUID_1.node());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The node value is: 8796630719078

```

**程序 2:**

```
// Java code to illustrate node() method

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

        // Displaying the node Value
        System.out.println("The node value is: "
                           + UUID_1.node());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The node value is: 145009316876108

```
# Java 中的 UUID 等于()方法，示例

> 原文:[https://www . geesforgeks . org/uuid-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-equals-method-in-java-with-examples/)

Java 中 **UUID 类**的 **equals()** 方法用于检查一个 UUID 与另一个的相等性。如果两个 UUID 一点一点地完全相同，则该方法返回真。

**语法:**

```
public boolean equals(Object uuidObj)
```

**参数:**该方法采用一个参数 **uuidObj** ，UUID_1 将与该参数进行比较。

**返回值:**如果两个 UUIDs 相同，则该方法返回**真**否则返回**假**。

下面的程序说明了 equals()方法的工作原理:

**程序 1:**

```
// Java code to illustrate equals() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating two UUIDs
        UUID UUID_1
            = UUID
                  .fromString(
                      "5fc03087-d265-11e7-b8c6-83e29cd24f4c");

        UUID UUID_2
            = UUID
                  .fromString(
                      "5fc03087-d265-11e7-b8c6-83e29cd24f4c");

        // Displaying the UUID values
        System.out.println("UUID_1: "
                           + UUID_1.clockSequence());
        System.out.println("UUID_2: "
                           + UUID_2.clockSequence());

        // Comparing both the UUIDs
        System.out.println("Are both UUID equal: "
                           + UUID_1.equals(UUID_2));
    }
}
```

**Output:**

```
UUID_1: 14534
UUID_2: 14534
Are both UUID equal: true

```

**程序 2:**

```
// Java code to illustrate equals() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating two UUIDs
        UUID UUID_1
            = UUID
                  .fromString(
                      "5fc03087-d265-11e7-b8c6-83e29cd24f4c");

        UUID UUID_2
            = UUID
                  .fromString(
                      "58e0a7d7-eebc-11d8-9669-0800200c9a66");

        // Displaying the UUID values
        System.out.println("UUID_1: "
                           + UUID_1.clockSequence());
        System.out.println("UUID_2: "
                           + UUID_2.clockSequence());

        // Comparing both the UUIDs
        System.out.println("Are both UUID equal: "
                           + UUID_1.equals(UUID_2));
    }
}
```

**Output:**

```
UUID_1: 14534
UUID_2: 5737
Are both UUID equal: false

```
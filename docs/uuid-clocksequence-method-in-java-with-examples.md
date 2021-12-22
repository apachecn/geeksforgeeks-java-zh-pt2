# Java 中的 UUID 时钟序列()方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-clock sequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-clocksequence-method-in-java-with-examples/)

Java 中 **UUID 类**的 **clockSequence()** 方法一般用来知道与这个 UUID 关联的时钟序列值。该 UUID 的时钟序列字段用于创建 14 位时钟序列值。

**语法:**

```
public int clockSequence()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**整数值**，它是与这个 UUID 相关的时钟序列值。

**异常:**如果这个 UUID 不是版本 1 的 UUID，方法抛出**不支持操作异常**。

下面的程序说明了 clockSequence()方法的工作原理:

**程序 1:**

```
// Java code to illustrate clockSequence() method

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

        // Displaying the clock sequence value
        System.out.println("The clock sequence value is: "
                           + UUID_1.clockSequence());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The clock sequence value is: 5737

```

**程序 2:**

```
// Java code to illustrate clockSequence() method

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
        System.out.println("The clock sequence value is: "
                           + UUID_1.clockSequence());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The clock sequence value is: 14534

```
# Java 中的 UUID 时间戳()方法，示例

> 原文:[https://www . geesforgeks . org/uuid-timestamp-in-Java-method-with-examples/](https://www.geeksforgeeks.org/uuid-timestamp-method-in-java-with-examples/)

Java 中 **UUID 类**的**时间戳()**方法一般用于获取与特定 UUID 相关联的时间戳值。

**语法:**

```
public long timestamp()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该 UUID 的时间戳值。

**异常:**如果这个 UUID 不是版本 1 UUID 的一部分，这个方法抛出**不支持操作异常**。

下面的程序说明了 timestamp()方法的工作原理:

**程序 1:**

```
// Java code to illustrate timestamp() method

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

        // Displaying the timestamp value
        System.out.println("The timestamp value is: "
                           + UUID_1.timestamp());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The timestamp value is: 133118681719810007

```

**程序 2:**

```
// Java code to illustrate timestamp() method

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

        // Displaying the timestamp Value
        System.out.println("The timestamp value is: "
                           + UUID_1.timestamp());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The timestamp value is: 137309646498050183

```
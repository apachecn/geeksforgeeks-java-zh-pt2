# Java 中的 UUID getlestingbits()方法示例

> 原文:[https://www . geeksforgeeks . org/uuid-getlestsiagnatbits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-getleastsignificantbits-method-in-java-with-examples/)

UUIDs 是 128 位的值。Java 中的 **UUID 类**的**getlestsimitantbits()**方法用于获取这个 UUID 的最低有效 64 位。

**语法:**

```
public long getLeastSignificantBits()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**整数值**，它是这个 128 值 UUID 的最低有效 64 位。

下面的程序说明了 getLeastSignificantBits()方法的工作原理:

**程序 1:**

```
// Java code to illustrate
// getLeastSignificantBits() method

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

        // Displaying the value of UUID
        System.out.println("The value is: "
                           + UUID_1.clockSequence());

        // Getting the least significant 64 bit
        System.out.println("The least significant 64 bit: "
                           + UUID_1
                                 .getLeastSignificantBits());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The value is: 5737
The least significant 64 bit: -7608541298835023258

```

**程序 2:**

```
// Java code to illustrate
// getLeastSignificantBits() method

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

        // Displaying the value of UUID
        System.out.println("The value is: "
                           + UUID_1.clockSequence());

        // Getting the least significant 64 bit
        System.out.println("The least significant 64 bit: "
                           + UUID_1.getLeastSignificantBits());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The value is: 5737
The least significant 64 bit: -7608541298835023258

```
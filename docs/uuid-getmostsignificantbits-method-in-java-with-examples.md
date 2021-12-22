# Java 中的 UUID getMostSignificantBits()方法示例

> 原文:[https://www . geeksforgeeks . org/uuid-getmostificantbits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-getmostsignificantbits-method-in-java-with-examples/)

UUIDs 是 128 位的值。Java 中的 **UUID 类**的**getmostectivititbits()**方法用来获取这个 UUID 的最高有效 64 位。

**语法:**

```
public long getMostSignificantBits()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**整数值**，它是这个 128 值 UUID 的最高有效 64 位。

下面的程序说明了 getMostSignificantBits()方法的工作原理:

**程序 1:**

```
// Java code to illustrate
// getMostSignificantBits() method

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

        // Getting the most significant 64 bit
        System.out.println("The most significant 64 bit: "
                           + UUID_1
                                 .getMostSignificantBits());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The value is: 5737
The most significant 64 bit: 6404303215985955288

```

**程序 2:**

```
// Java code to illustrate
// getMostSignificantBits() method

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

        // Getting the most significant 64 bit
        System.out.println("The most significant 64 bit: "
                           + UUID_1.getMostSignificantBits());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The value is: 5737
The most significant 64 bit: 6404303215985955288

```
# UUID 用示例比较 Java 中的方法

> 原文:[https://www . geesforgeks . org/uuid-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-compareto-method-in-java-with-examples/)

Java 中 **UUID 类**的 **compareTo()** 方法用于将一个 UUID 值与另一个指定的 UUID 值进行比较。如果 UUID 小于该值，则返回-1；如果 UUID 等于该值，则返回 0；如果 UUID 大于该值，则返回 1。

**语法:**

```java
UUID_1.compareTo(UUID_2)
```

**参数:**该方法取一个参数 **UUID_2** ，与 UUID_1 进行比较。

**返回值:**该方法返回 **-1、0 或 1** ，具体取决于该 UUID_1 是否小于、等于或大于另一个 UUID_2。

下面的程序说明了 compareTo()方法的工作原理:

**程序 1:** 检查两个 UUIDs 是否相等。

```java
// Java code to illustrate compareTo() method

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
        System.out.println("Comparison Value: "
                           + UUID_1.compareTo(UUID_2));
    }
}
```

**Output:**

```java
UUID_1: 14534
UUID_2: 14534
Comparison Value: 0

```

**程序 2:** 当 UUID_1 小于 UUID_2 时，方法返回-1。

```java
// Java code to illustrate compareTo() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Creating two UUIDs
        UUID UUID_1
            = UUID
                  .fromString(
                      "58e0a7d7-eebc-11d8-9669-0800200c9a66");

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
        System.out.println("Comparison Value: "
                           + UUID_1.compareTo(UUID_2));
    }
}
```

**Output:**

```java
UUID_1: 5737
UUID_2: 14534
Comparison Value: -1

```

**程序 3:** 当 UUID_1 大于 UUID_2 时，方法返回 1。

```java
// Java code to illustrate compareTo() method

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
        System.out.println("Comparison Value: "
                           + UUID_1.compareTo(UUID_2));
    }
}
```

**Output:**

```java
UUID_1: 14534
UUID_2: 5737
Comparison Value: 1

```
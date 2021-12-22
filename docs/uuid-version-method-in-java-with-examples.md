# UUID 版()Java 方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-version-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uuid-version-method-in-java-with-examples/)

每个 UUID 都有一个版本号来描述这个 UUID 的产生。Java 中 **UUID 类**的**版本()**方法一般用来获取与这个 UUID 关联的版本号。

**语法:**

```
public int version()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个 **int 值**，这是与这个 UUID 相关的版本号。

下面的程序说明了 version()方法的工作原理:

**程序 1:**

```
// Java code to illustrate version() method

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

        // Displaying the version number
        System.out.println("The version number is: "
                           + UUID_1.version());
    }
}
```

**Output:**

```
UUID: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The version number is: 1

```

**程序 2:**

```
// Java code to illustrate version() method

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

        // Displaying the version Value
        System.out.println("The version number is: "
                           + UUID_1.version());
    }
}
```

**Output:**

```
UUID: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The version number is: 1

```
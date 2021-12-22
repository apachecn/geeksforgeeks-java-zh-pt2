# Java 中的 UUID fromString()方法，带示例

> 原文:[https://www . geesforgeks . org/uuid-from string-in-Java-method-with-examples/](https://www.geeksforgeeks.org/uuid-fromstring-method-in-java-with-examples/)

Java 中的 **UUID 类**的 **fromString()** 方法用于从相同的标准字符串表示创建 UUID。

**语法:**

```
public static UUID fromString(String UUID_name)
```

**参数:**该方法取一个参数 **UUID_name** ，这是 UUID 的字符串表示。

**返回值:**该方法返回从指定字符串创建的实际的 **UUID** 。

**异常:**如果通过了无效的 *UUID_name* ，则该方法抛出 **IllegalArgumentException** 。

下面的程序说明了 fromString()方法的工作原理:

**程序 1:**

```
// Java code to illustrate fromString() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Get the string
        String UUID_name
            = "5fc03087-d265-11e7-b8c6-83e29cd24f4c";

        // Displaying the UUID
        System.out.println("The specified String is: "
                           + UUID_name);

        // Creating the UUID
        UUID UUID_1
            = UUID
                  .fromString(UUID_name);

        // Displaying the UUID
        System.out.println("The UUID from"
                           + " specified String: "
                           + UUID_1);
    }
}
```

**Output:**

```
The specified String is: 5fc03087-d265-11e7-b8c6-83e29cd24f4c
The UUID from specified String: 5fc03087-d265-11e7-b8c6-83e29cd24f4c

```

**程序 2:**

```
// Java code to illustrate fromString() method

import java.util.*;

public class UUID_Demo {
    public static void main(String[] args)
    {

        // Get the string
        String UUID_name
            = "58e0a7d7-eebc-11d8-9669-0800200c9a66";

        // Displaying the UUID
        System.out.println("The specified String is: "
                           + UUID_name);

        // Creating the UUID
        UUID UUID_1
            = UUID
                  .fromString(UUID_name);

        // Displaying the UUID
        System.out.println("The UUID from"
                           + " specified String: "
                           + UUID_1);
    }
}
```

**Output:**

```
The specified String is: 58e0a7d7-eebc-11d8-9669-0800200c9a66
The UUID from specified String: 58e0a7d7-eebc-11d8-9669-0800200c9a66

```
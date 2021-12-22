# Java 中的 ZoneOffset ofOffset()方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-ofoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-ofoffset-method-in-java-with-examples/)

**ZoneOffset** 类的 **ofOffset()** 方法，用于获取一个环绕偏移的 ZoneOffset 实例。如果在此方法中传递的前缀是“格林尼治标准时间”、“世界协调时”或“世界时”，则返回非零偏移量，如果前缀为空，则返回区域偏移量。

**语法:**

```java
ublic static ZoneId ofOffset(String prefix,
                              ZoneOffset offset)

```

**参数:**该方法接受两个参数**前缀**和**偏移量**，其中前缀代表时区标识，偏移量代表偏移量。

**返回值:**这个方法返回 zoneId。

**异常:**如果前缀不是“GMT”、“UTC”或“UT”中的一个，此方法将引发 **IllegalArgumentException** 。

下面的程序说明了 ofOffset()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZoneOffset.ofOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.ofOffset("UTC",
                              ZoneOffset.UTC);

        // Print the ZoneOffset
        System.out.println("ZoneOffset: "
                           + zoneId);
    }
}
```

**输出:**

```java
ZoneOffset: UTC

```

**程序二:**

```java
// Java program to demonstrate
// ZoneOffset.ofOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.ofOffset("GMT",
                              ZoneOffset.MAX);
        System.out.println("ZoneOffset: "
                           + zoneId);
    }
}
```

**输出:**

```java
ZoneOffset: GMT+18:00

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneId.html#ofOffset-java.lang.String-java.time.ZoneOffset-)
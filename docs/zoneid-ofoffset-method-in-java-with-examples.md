# Java 中的 ZoneId ofOffset()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-ofoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-ofoffset-method-in-java-with-examples/)

**ZoneId** 类的 **ofOffset()** 方法用于获取一个包装偏移量的 ZoneId 实例。如果在此方法中传递的前缀是“格林尼治标准时间”、“世界协调时”或“世界协调时”，则返回非零偏移量，如果前缀为空，则返回区域偏移量。

**语法:**

```java
ublic static ZoneId ofOffset(String prefix,
                              ZoneOffset offset)

```

**参数:**该方法接受两个参数**前缀**和**偏移量**，其中前缀代表时区标识，偏移量代表偏移量。

**返回值:**这个方法返回 zoneId。

**异常:**如果前缀不是“GMT”、“UTC”或“UT”中的一个，此方法将引发 **IllegalArgumentException** 。

以下程序说明了 ofOffset()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZoneId.ofOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.ofOffset("UTC",
                              ZoneOffset.UTC);

        // print result
        System.out.println("ZoneId:"
                           + zoneId);
    }
}
```

**Output:**

```java
ZoneId:UTC

```

**程序 2:**

```java
// Java program to demonstrate
// ZoneId.ofOffset() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.ofOffset("GMT",
                              ZoneOffset.MAX);

        // print result
        System.out.println("ZoneId:"
                           + zoneId);
    }
}
```

**Output:**

```java
ZoneId:GMT+18:00

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # ofofoffset(Java . lang . string，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#ofOffset(java.lang.String, java.time.ZoneOffset))
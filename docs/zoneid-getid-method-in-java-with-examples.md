# Java 中的 ZoneId getId()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-getid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-getid-method-in-java-with-examples/)

Java 中 **ZoneId** 类的 **getId()** 方法用于获取唯一定义该对象的唯一时区 Id。

**语法:**

```java
public String getId(Object obj)

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回时区唯一**标识**。

下面的程序说明了 getId()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZoneId.getId() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Europe/Paris");

        // get and print Id
        System.out.println("Id: "
                           + zoneId.getId());
    }
}
```

**Output:**

```java
Id: Europe/Paris

```

**程序 2:**

```java
// Java program to demonstrate
// ZoneId.getId() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Asia/Calcutta");

        // get and print Id
        System.out.println("Id: "
                           + zoneId.getId());
    }
}
```

**Output:**

```java
Id: Asia/Calcutta

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # getId()](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#getId())
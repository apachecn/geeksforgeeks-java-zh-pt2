# Java 中的 ZoneId systemDefault()方法，示例

> 原文:[https://www . geesforgeks . org/zoneid-system default-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-systemdefault-method-in-java-with-examples/)

Java 中 **ZoneId** 类的 **systemDefault()** 方法用于返回系统默认时区。

**语法:**

```java
public String systemDefault()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回区域标识。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果转换后的区域标识的格式无效，它将引发此异常。
*   **区域规则异常**–如果找不到转换后的区域标识，将引发该异常。

以下程序说明了 systemDefault()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZoneId.systemDefault() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.systemDefault();

        // printresult
        System.out.println("ZoneId: "
                           + zoneId);
    }
}
```

**Output:**

```java
ZoneId: Etc/UTC

```

**程序 2:**

```java
// Java program to demonstrate
// ZoneId.systemDefault() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.systemDefault();

        if (zoneId.getId().equals("Etc/UTC"))
            System.out.println("This zone is Etc/UTC");
        else
            System.out.println("This zone is not Etc/UTC");
    }
}
```

**Output:**

```java
This zone is Etc/UTC

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # systemDefault()](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#systemDefault())
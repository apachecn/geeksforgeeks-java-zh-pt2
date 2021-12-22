# Java 中的 ZoneId toString()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-tostring-method-in-java-with-examples/)

Java 中 **ZoneId** 类的 **toString()** 方法用于使用 Id 将该区域作为字符串返回。

**语法:**

```
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回该时区标识的字符串表示形式。

下面的程序说明了 toString()方法:

**程序 1:**

```
// Java program to demonstrate
// ZoneId.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Europe/Paris");

        // apply toString()
        System.out.println("ZoneId: "
                           + zoneId.toString());
    }
}
```

**Output:**

```
ZoneId: Europe/Paris

```

**程序 2:**

```
// Java program to demonstrate
// ZoneId.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Asia/Calcutta");

        // apply toString()
        System.out.println("ZoneId: "
                           + zoneId.toString());
    }
}
```

**Output:**

```
ZoneId: Asia/Calcutta

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#toString())
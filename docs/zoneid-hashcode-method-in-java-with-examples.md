# Java 中的 ZoneId hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-hashcode-method-in-java-with-examples/)

Java 中 **ZoneId** 类的 **hashCode()** 方法用于返回该 ZoneId 的唯一 hashCode。

**语法:**

```
public int hashCode(Object obj)

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回**一个 int** ，代表 hashCode。

下面的程序说明了 hashCode()方法:
**程序 1:**

```
// Java program to demonstrate
// ZoneId.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Europe/Paris");

        // get and print hashcode
        System.out.println("hashcode: "
                           + zoneId.hashCode());
    }
}
```

**Output:**

```
hashcode: -672549154

```

**程序 2:**

```
// Java program to demonstrate
// ZoneId.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Asia/Calcutta");

        // get and print hashcode
        System.out.println("hashcode: "
                           + zoneId.hashCode());
    }
}
```

**Output:**

```
hashcode: -681304890

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#hashCode())
# Java 中的 ZonedDateTime hashCode()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-hashcode-method-in-java-with-examples/)

一个 **ZonedDateTime** 类的 **hashCode()** 方法用来获取这个 ZonedDateTime 的 hashCode。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用这个唯一的代码搜索一个对象。

**语法:**

```
public ZoneId hashCode()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**整数值**代表一个合适的哈希码。

下面的程序说明了 hashCode()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get hashcode
        int value = zoneddatetime.hashCode();

        // print result
        System.out.println("hashcode:" + value);
    }
}
```

**输出:**

```
hashcode:1966859253

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get hashcode
        int value = zoneddatetime.hashCode();

        // print result
        System.out.println("hashcode:" + value);
    }
}
```

**输出:**

```
hashcode:1110445649

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#hashCode())
# Java 中的 OffsetTime equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/offsettime-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-equals-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **equals()** 方法检查这个时间是否等于另一个时间。如果相等则返回 true，否则返回 false。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受单个强制参数 **obj** ，该参数指定将与之进行比较的其他时间。

**返回值:**如果两个时间相等则返回真，否则返回假。

以下程序说明了*等于()*的方法:

**程序 1 :**

```java
// Java program to demonstrate the equals() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time1
            = OffsetTime.parse("15:30:30+07:00");

        // Parses the time
        OffsetTime time2
            = OffsetTime.parse("15:30:30+07:00");

        // gets the offset time1
        System.out.println("time1: "
                           + time1);

        // gets the offset time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 when compared"
                           + " to time2 returns: "
                           + time1.equals(time2));
    }
}
```

**输出:**

```java
time1: 15:30:30+07:00
time1: 15:30:30+07:00
time1 when compared to time2 returns: true

```

**程序二** :

```java
// Java program to demonstrate the equals() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time1
            = OffsetTime.parse("15:30:30+07:00");

        // Parses the time
        OffsetTime time2
            = OffsetTime.parse("12:10:30+07:00");

        // gets the offset time1
        System.out.println("time1: "
                           + time1);

        // gets the offset time2
        System.out.println("time1: "
                           + time2);

        System.out.println("time1 when compared"
                           + " to time2 returns: "
                           + time1.equals(time2));
    }
}
```

**输出:**

```java
time1: 15:30:30+07:00
time1: 12:10:30+07:00
time1 when compared to time2 returns: false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettine . html # compare to-Java . time . offsettine-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#compareTo-java.time.OffsetTime-)
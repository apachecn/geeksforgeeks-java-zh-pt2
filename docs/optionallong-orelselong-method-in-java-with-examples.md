# 选项 Java 中的 long or LSE(long)方法，示例

> 原文:[https://www . geesforgeks . org/optional long-or elselong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-orelselong-method-in-java-with-examples/)

**or LSE(long)**方法帮助我们获取这个 OptionalLong 对象中的值。如果该选项中没有值，则该方法返回作为参数传递的值。

**语法:**

```java
public long orElse(long other)

```

**参数:**如果不存在值，该方法接受要返回的长值。

**返回值:**该方法返回值，如果存在，否则为其他。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalLong.orElse(long) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong opLong = OptionalLong.of(452146);

        // get value using orElse
        long value = opLong.orElse(13421);

        // prlong value
        System.out.println("value: " + value);
    }
}
```

**Output:**

```java
value: 452146

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalLong.orElse(long) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong opLong = OptionalLong.empty();

        // get value using orElse
        long value = opLong.orElse(13421);

        // prlong value
        System.out.println("value: " + value);
    }
}
```

**Output:**

```java
value: 13421

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # orElse(long)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#orElse(long))
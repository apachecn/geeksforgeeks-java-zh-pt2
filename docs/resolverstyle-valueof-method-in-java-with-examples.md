# Java 中 ResolverStyle valueOf()方法示例

> 原文:[https://www . geesforgeks . org/resolver style-value of-method-in-Java-with-examples/](https://www.geeksforgeeks.org/resolverstyle-valueof-method-in-java-with-examples/)

**解析器样式枚举**的 **valueOf()** 方法用于获取具有指定名称的该类型解析器样式的枚举值。

**语法:**

```java
public static ResolverStyle valueOf(String name)

```

**参数:**该方法接受一个**名称**作为参数，该参数是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的**枚举常量**。

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException** :如果这个枚举类型没有指定名称的常量。
*   **NullPointRexception**:如果参数为空。

以下程序说明了 ResolverStyle.valueOf()方法:
**程序 1:**

```java
// Java program to demonstrate
// ResolverStyle.valueOf() method

import java.time.format.ResolverStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get ResolverStyle instance
        ResolverStyle resolverStyle
            = ResolverStyle.valueOf("SMART");

        // Print the result
        System.out.println("ResolverStyle: "
                           + resolverStyle);
    }
}
```

**Output:**

```java
ResolverStyle: SMART

```

**程序 2:**

```java
// Java program to demonstrate
// ResolverStyle.valueOf() method

import java.time.format.ResolverStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get ResolverStyle instance
        ResolverStyle resolverStyle
            = ResolverStyle.valueOf("LENIENT");

        // Print the result
        System.out.println("ResolverStyle: "
                           + resolverStyle);
    }
}
```

**Output:**

```java
ResolverStyle: LENIENT

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/resolver style . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/ResolverStyle.html)
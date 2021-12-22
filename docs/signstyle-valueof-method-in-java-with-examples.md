# Java 中 SignStyle valueOf()方法，示例

> 原文:[https://www . geesforgeks . org/sign style-value of-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/signstyle-valueof-method-in-java-with-examples/)

**SignStyle 枚举**的 **valueOf()** 方法用于返回具有指定名称的该类型 SignStyle 的枚举。

**语法:**

```java
public static SignStyle valueOf(String name)

```

**参数:**该方法接受一个**名称**作为参数，该参数是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的**枚举常量**。

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException** :如果这个枚举类型没有指定名称的常量。
*   **NullPointRexception**:如果参数为空。

下面的程序说明了 SignStyle.valueOf()方法:
**程序 1:**

```java
// Java program to demonstrate
// SignStyle.valueOf() method

import java.time.format.SignStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get SignStyle instance
        SignStyle signStyle
            = SignStyle.valueOf("NOT_NEGATIVE");

        // Print the result
        System.out.println("SignStyle: "
                           + signStyle);
    }
}
```

**Output:**

```java
SignStyle: NOT_NEGATIVE

```

**程序 2:**

```java
// Java program to demonstrate
// SignStyle.valueOf() method

import java.time.format.SignStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get SignStyle instance
        SignStyle signStyle
            = SignStyle.valueOf("NEVER");

        // Print the result
        System.out.println("SignStyle: "
                           + signStyle);
    }
}
```

**Output:**

```java
SignStyle: NEVER

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/sign style . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/SignStyle.html)
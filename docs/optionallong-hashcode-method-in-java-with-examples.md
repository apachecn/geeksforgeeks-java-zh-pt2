# 选项 Java 中的 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/option allong-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-hashcode-method-in-java-with-examples/)

**hashCode()** 方法帮助我们获取值的 hash 码，如果 Long 值存在，则为 0(零)，如果 OptionalLong 对象中没有 Long 值，则为 0(零)。

**语法:**

```java
public int hashCode()

```

**参数:**此方法接受不接受任何参数。

**返回值:**该方法返回当前值的哈希码值，如果没有值则返回 0。

下面的程序说明了 hashCode()方法:

**程序 1:**

```java
// Java program to demonstrate
// OptionalLong.hashCode() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong instance
        OptionalLong opLong
            = OptionalLong.of(253255);

        System.out.println("OptionalLong: "
                           + opLong.toString());

        // get hashCode value using hashCode()
        System.out.println("HashCode value: "
                           + opLong.hashCode());
    }
}
```

**输出:**

```java
OptionalLong: OptionalLong[253255]
HashCode value: 253255

```

**程序二:**

```java
// Java program to demonstrate
// OptionalLong.hashCode() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong instance
        OptionalLong opLong
            = OptionalLong.empty();

        System.out.println("OptionalLong: "
                           + opLong.toString());

        // get hashCode value using hashCode()
        System.out.println("HashCode value: "
                           + opLong.hashCode());
    }
}
```

**输出:**

```java
OptionalLong: OptionalLong.empty
HashCode value: 0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#hashCode())
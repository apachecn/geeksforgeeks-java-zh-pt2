# Java 中的 OptionalDouble hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/optionaldouble-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-hashcode-method-in-java-with-examples/)

**hashCode()** 方法帮助我们获取值的哈希代码，如果存在 Double 值，则为 0(零)，如果 OptionalDouble 对象中不存在 Double 值，则为 0(零)。

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
// OptionalDouble.hashCode() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble instance
        OptionalDouble opDouble
            = OptionalDouble.of(253255.432525);

        System.out.println("OptionalDouble: "
                           + opDouble.toString());

        // get hashCode value using hashCode()
        System.out.println("HashCode value: "
                           + opDouble.hashCode());
    }
}
```

**输出:**

```java
OptionalDouble: OptionalDouble[253255.432525]
HashCode value: 885080309

```

**程序二:**

```java
// Java program to demonstrate
// OptionalDouble.hashCode() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble instance
        OptionalDouble opDouble
            = OptionalDouble.empty();

        System.out.println("OptionalDouble: "
                           + opDouble.toString());

        // get hashCode value using hashCode()
        System.out.println("HashCode value: "
                           + opDouble.hashCode());
    }
}
```

**输出:**

```java
OptionalDouble: OptionalDouble.empty
HashCode value: 0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldoruble . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#hashCode())
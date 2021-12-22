# 选项 Java 中(长)方法的一个例子

> 原文:[https://www . geesforgeks . org/option allong-of long-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-oflong-method-in-java-with-examples/)

(长)方法的**帮助我们获得一个包含长值的**选项龙**对象，该长值作为参数传递给该方法。**

**语法:**

```java
public static OptionalLong of(long value)

```

**参数:**该方法接受一个**长值**作为参数，该参数将被设置为返回的选项龙对象。

**返回值:**该方法返回一个存在值的**选项龙**。

以下程序举例说明(长)法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalLong.of(long) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // Create a OptionalLong instance
        // using of() method
        OptionalLong opLong
            = OptionalLong.of(45213246);

        // Get value of this OptionalLong instance
        System.out.println("OptionalLong: "
                           + opLong);
    }
}
```

**Output:**

```java
OptionalLong: OptionalLong[45213246]

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalLong.of(long) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // Create a OptionalLong instance
        // using of() method
        OptionalLong opLong
            = OptionalLong.of(21438999);

        // Get value of this OptionalLong instance
        System.out.println("OptionalLong: "
                           + opLong);
    }
}
```

**Output:**

```java
OptionalLong: OptionalLong[21438999]

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # of(long)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#of(long))
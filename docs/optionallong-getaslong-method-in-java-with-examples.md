# 选项 Java 中的 getAsLong()方法，带示例

> 原文:[https://www . geesforgeks . org/option allong-getaslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-getaslong-method-in-java-with-examples/)

**选项龙**帮助我们创建一个可能包含也可能不包含长值的对象。 **getAsLong()** 方法返回值如果 OptionalLong 对象中有值，否则抛出**nosucheelementexception**。

**语法:**

```java
public long getAsLong()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该选项描述的值。

**异常:**如果不存在值，该方法抛出 **NoSuchElementException**

下面的程序说明了 getAsLong()方法:

**程序 1:**

```java
// Java program to demonstrate
// OptionalLong.getAsLong() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // Create an OptionalLong instance
        OptionalLong opLong = OptionalLong.of(445325);

        System.out.println("OptionalLong: "
                           + opLong.toString());

        // Get value in this instance
        // using getAsLong()
        System.out.println("Value in OptionalLong = "
                           + opLong.getAsLong());
    }
}
```

**输出:**

```java
OptionalLong: OptionalLong[445325]
Value in OptionalLong = 445325

```

**程序二:**

```java
// Java program to demonstrate
// OptionalLong.getAsLong() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        try {

            // Create an OptionalLong instance
            OptionalLong opLong = OptionalLong.empty();

            System.out.println("OptionalLong: "
                               + opLong.toString());

            // Get value in this instance
            // using getAsLong()
            System.out.println("Value in OptionalLong = "
                               + opLong.getAsLong());
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
OptionalLong: OptionalLong.empty
Exception: java.util.NoSuchElementException: No value present

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # getAsLong()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#getAsLong())
# Java 中可选的 toString()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-tostring-method-in-java-with-examples/)

**的 **toString()** 法[爪哇](https://www.geeksforgeeks.org/java-util-package-java/)。Java 中的可选类**用来获取这个可选实例的字符串表示。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个可选实例的**字符串**表示。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.toString() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.of(452146);

        // get value using toString
        String value = op.toString();

        // print value
        System.out.println("String Representation: "
                           + value);
    }
}
```

**Output:**

```java
String Representation: Optional[452146]

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.toString() method

import java.util.Optional;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.empty();

        // get value using toString
        String value = op.toString();

        // print value
        System.out.println("String Representation: "
                           + value);
    }
}
```

**Output:**

```java
String Representation: Optional.empty

```

**参考文献:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # toString–
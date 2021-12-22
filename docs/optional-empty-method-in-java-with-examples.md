# Java 中可选的空()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-empty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-empty-method-in-java-with-examples/)

**空()**法**法[法](https://www.geeksforgeeks.org/java-util-package-java/)。Java 中的可选类**用来获取这个可选类的一个空实例。此实例不包含任何值。

**语法:**

```java
public static <T> 
  Optional<T> empty()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个可选类的一个**空实例**。

以下程序举例说明空()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.empty() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.empty();

        // print value
        System.out.println("Optional: "
                           + op);
    }
}
```

**Output:**

```java
Optional: Optional.empty

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.empty() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<String> op
            = Optional.empty();

        // print value
        System.out.println("Optional: "
                           + op);
    }
}
```

**Output:**

```java
Optional: Optional.empty

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # empty–](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#empty--)
# 选项 Java 中的 toString()方法，带示例

> 原文:[https://www . geesforgeks . org/optional int-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-tostring-method-in-java-with-examples/)

**toString()** 方法帮助我们获得这个选项的非空字符串表示。这种非空字符串表示形式适合于调试。确切的呈现格式未指定，可能因实现和版本而异。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个实例的字符串表示。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalInt.toString() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt
            = OptionalInt.of(452146);

        // get value using toString
        String value = opInt.toString();

        // print value
        System.out.println("String Representation: "
                           + value);
    }
}
```

**Output:**

```java
String Representation: OptionalInt[452146]

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalInt.toString() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt
            = OptionalInt.empty();

        // get value using toString
        String value = opInt.toString();

        // print value
        System.out.println("String Representation: "
                           + value);
    }
}
```

**Output:**

```java
String Representation: OptionalInt.empty

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#toString())
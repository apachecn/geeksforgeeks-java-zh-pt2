# OptionalInt 是 Java 中的 Present()方法，带有示例

> 原文:[https://www . geesforgeks . org/optional int-is present-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-ispresent-method-in-java-with-examples/)

**选项链接**帮助我们创建一个可能包含也可能不包含整数值的对象。 **isPresent()** 方法帮助我们得到 Int 值是否存在于 OptionalInt 对象中的答案。如果此对象中存在 int 值，则此方法返回 true，否则返回 false。

**语法:**

```java
public boolean isPresent()

```

**参数:**此方法不接受任何内容。

**返回值:**如果存在 int 值，则该方法返回 true，否则返回 false

下面的程序说明了 isPresent()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalInt.isPresent() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt = OptionalInt.of(12345);

        // get value using isPresent()
        System.out.println("OptionalInt has a value= "
                           + opInt.isPresent());
    }
}
```

**Output:**

```java
OptionalInt has a value= true

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalInt.isPresent() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt = OptionalInt.empty();

        // try to get that value is present or not
        boolean response = opInt.isPresent();

        if (response)
            System.out.println("Value present");
        else
            System.out.println("Value absent");
    }
}
```

**Output:**

```java
Value absent

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # isPresent()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#isPresent())
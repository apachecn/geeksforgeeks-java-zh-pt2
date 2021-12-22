# OptionalLong 是 Java 中的 Present()方法，带有示例

> 原文:[https://www . geesforgeks . org/option allong-is present-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-ispresent-method-in-java-with-examples/)

**选项龙**帮助我们创建一个可能包含也可能不包含长值的对象。 **isPresent()** 方法帮助我们得到一个答案，一个值是否存在于一个对象的选项中。如果此对象中存在长值，则此方法返回 true，否则返回 false。

**语法:**

```java
public boolean isPresent()

```

**参数:**此方法不接受任何内容。

**返回值:**如果存在值，则该方法返回真，否则返回假

下面的程序说明了 isPresent()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalLong.isPresent() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong opLong
            = OptionalLong.of(45213246);

        // get value using isPresent()
        System.out.println("OptionalLong "
                           + "has a value= "
                           + opLong.isPresent());
    }
}
```

**Output:**

```java
OptionalLong has a value= true

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalLong.isPresent() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong opLong = OptionalLong.empty();

        // try to get that value is present or not
        boolean response = opLong.isPresent();

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

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # isPresent()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#isPresent())
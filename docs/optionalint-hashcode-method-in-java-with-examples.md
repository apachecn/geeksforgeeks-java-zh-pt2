# 选项 Java 中的 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/optional int-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-hashcode-method-in-java-with-examples/)

**hashCode()** 方法帮助我们获取值的哈希代码，如果存在 Int 值，否则为 0(零)，如果 OptionalInt 对象中不存在 Int 值。

**语法:**

```
public int hashCode()

```

**参数:**此方法接受不接受任何参数。

**返回值:**该方法返回当前值的哈希码值，如果没有值则返回 0。

下面的程序说明了 hashCode()方法:

**程序 1:**

```
// Java program to demonstrate
// OptionalInt.hashCode() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt instance
        OptionalInt opInt
            = OptionalInt.of(253);

        System.out.println("OptionalInt: "
                           + opInt.toString());

        // get hashCode value using hashCode()
        System.out.println("HashCode value: "
                           + opInt.hashCode());
    }
}
```

**输出:**

```
OptionalInt: OptionalInt[253]
HashCode value: 253

```

**程序二:**

```
// Java program to demonstrate
// OptionalInt.hashCode() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt instance
        OptionalInt opInt
            = OptionalInt.empty();

        System.out.println("OptionalInt: "
                           + opInt.toString());

        // get hashCode value using hashCode()
        System.out.println("HashCode value: "
                           + opInt.hashCode());
    }
}
```

**输出:**

```
OptionalInt: OptionalInt.empty
HashCode value: 0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#hashCode())
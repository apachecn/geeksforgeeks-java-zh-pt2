# 选项 Java 中的 getAsInt()方法，带示例

> 原文:[https://www . geesforgeks . org/optional int-getasint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-getasint-method-in-java-with-examples/)

**选项链接**帮助我们创建一个可能包含也可能不包含整数值的对象。 **getAsInt()** 方法返回值如果 OptionalInt 对象中有值，否则抛出 **NoSuchElementException** 。

**语法:**

```
public int getAsInt()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该选项描述的值。

**异常:**如果不存在值，该方法抛出 **NoSuchElementException**

下面的程序说明 getAsInt()方法:

**程序 1:**

```
// Java program to demonstrate
// OptionalInt.getAsInt() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // Create an OptionalInt instance
        OptionalInt opInt = OptionalInt.of(45);

        System.out.println("OptionalInt: "
                           + opInt.toString());

        // Get value in this instance
        // using getAsInt()
        System.out.println("Value in OptionalInt = "
                           + opInt.getAsInt());
    }
}
```

**输出:**

```
OptionalInt: OptionalInt[45]
Value in OptionalInt = 45

```

**程序二:**

```
// Java program to demonstrate
// OptionalInt.getAsInt() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        try {

            // Create an OptionalInt instance
            OptionalInt opInt = OptionalInt.empty();

            System.out.println("OptionalInt: "
                               + opInt.toString());

            // Get value in this instance
            // using getAsInt()
            System.out.println("Value in OptionalInt = "
                               + opInt.getAsInt());
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
OptionalInt: OptionalInt.empty
Exception: java.util.NoSuchElementException: No value present

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # getAsInt()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#getAsInt())
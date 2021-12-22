# Java 中的 OptionalLong equals()方法，示例

> 原文:[https://www . geesforgeks . org/optional long-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-equals-method-in-java-with-examples/)

**选项龙**帮助我们创建一个可能包含也可能不包含长值的对象。 **equals(Object obj)** 方法帮助我们将这个 OptionalLong 对象与作为参数传递的对象进行比较，如果对象相等，则返回 true。

另一个对象被认为等于这个选项龙，如果:

*   It is also an option dragon, and;
*   The value or does not exist in both instances;
*   The present value is "equal" to each other through = =.

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该方法接受一个**对象**，它是一个待测对象是否相等。

**返回值:**如果另一个对象“等于”这个对象，这个方法返回真，否则返回假。

下面的程序说明了 equals(对象对象)方法:

**程序 1:**

```
// Java program to demonstrate
// OptionalLong.equals(Object obj) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // Create first OptionalLong object
        OptionalLong opLong1
            = OptionalLong.of(45213246);

        System.out.println("OptionalLong 1: "
                           + opLong1.toString());

        // Create second OptionalLong object
        OptionalLong opLong2
            = OptionalLong.of(45213246);

        System.out.println("OptionalLong 2: "
                           + opLong2.toString());

        // Check if these two objects are equal
        // using equals(Object obj)
        System.out.println("Are both objects equal: "
                           + opLong1.equals(opLong2));
    }
}
```

**输出:**

```
OptionalLong 1: OptionalLong[45213246]
OptionalLong 2: OptionalLong[45213246]
Are both objects equal: true

```

**程序二:**

```
// Java program to demonstrate
// OptionalLong.equals(Object obj) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {
        // Create first OptionalLong object
        OptionalLong opLong1
            = OptionalLong.of(317946492);

        System.out.println("OptionalLong 1: "
                           + opLong1.toString());

        // Create second OptionalLong object
        OptionalLong opLong2
            = OptionalLong.of(45213246);

        System.out.println("OptionalLong 2: "
                           + opLong2.toString());

        // Check if these two objects are equal
        // using equals(Object obj)
        System.out.println("Are both objects equal: "
                           + opLong1.equals(opLong2));
    }
}
```

**输出:**

```
OptionalLong 1: OptionalLong[317946492]
OptionalLong 2: OptionalLong[45213246]
Are both objects equal: false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # equals？(对象对象)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#equals(Object obj))
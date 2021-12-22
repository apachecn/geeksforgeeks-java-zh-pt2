# 选项 Java 中的空()方法，带示例

> 原文:[https://www . geesforgeks . org/optional long-empty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-empty-method-in-java-with-examples/)

**选项龙**帮助我们创建一个可能包含也可能不包含长值的对象。 **empty()** 方法返回一个空的 OptionalLong 实例。此选项没有值。所以我们可以说这个方法帮助我们创建了一个空的 OptionalLong 对象。

**语法:**

```
public static OptionalLong empty()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个空的选项龙。

下面程序举例说明空()方法:

**程序 1:**

```
// Java program to demonstrate
// OptionalLong.empty() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        // using empty method
        OptionalLong opLong
            = OptionalLong.empty();

        // prLong OptionalLong
        System.out.println("OptionalLong: "
                           + opLong.toString());
    }
}
```

**输出:**

```
OptionalLong: OptionalLong.empty

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # empty()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#empty())
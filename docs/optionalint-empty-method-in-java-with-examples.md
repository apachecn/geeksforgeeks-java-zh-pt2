# 选项 Java 中的空()方法，带示例

> 原文:[https://www . geeksforgeeks . org/optional int-empty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-empty-method-in-java-with-examples/)

**选项链接**帮助我们创建一个可能包含也可能不包含整数值的对象。 **empty()** 方法返回一个空的 OptionalInt 实例。此选项没有值。所以我们可以说这个方法帮助我们创建了一个空的 OptionalInt 对象。

**语法:**

```
public static OptionalInt empty()
```

**参数:**此方法不接受任何内容。
**返回值:**这个方法返回一个空的选项。

下面程序举例说明空()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// OptionalInt.empty() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        // using empty method
        OptionalInt opInt
            = OptionalInt.empty();

        // Print the created instance
        System.out.println("OptionalInt: "
                           + opInt.toString());
    }
}
```

**Output:** 

```
OptionalInt: OptionalInt.empty
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # empty()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#empty())
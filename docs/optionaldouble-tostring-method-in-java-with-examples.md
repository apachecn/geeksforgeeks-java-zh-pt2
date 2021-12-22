# Java 中的 OptionalDouble toString()方法，带示例

> 原文:[https://www . geesforgeks . org/optionaldouble-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-tostring-method-in-java-with-examples/)

**toString()** 方法帮助我们获得这个 OptionalDouble 的非空字符串表示。这种非空字符串表示形式适合于调试。确切的呈现格式未指定，可能因实现和版本而异。

**语法:**

```
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个实例的字符串表示。

下面的程序说明了 toString()方法:
**程序 1:**

```
// Java program to demonstrate
// OptionalDouble.toString() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble
            = OptionalDouble.of(.3203);

        // get value using toString
        String value = opDouble.toString();

        // print value
        System.out.print("Value: " + value);
    }
}
```

**Output:**

```
Value: OptionalDouble[0.3203]

```

**程序 2:**

```
// Java program to demonstrate
// OptionalDouble.toString() method
import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a empty OptionalDouble
        OptionalDouble opDouble
            = OptionalDouble.empty();

        // get value using toString
        String value = opDouble.toString();

        // print value
        System.out.print("Value: " + value);
    }
}
```

**Output:**

```
Value: OptionalDouble.empty

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#toString())
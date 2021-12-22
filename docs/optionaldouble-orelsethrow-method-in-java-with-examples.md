# Java 中的 OptionalDouble orElseThrow()方法，带示例

> 原文:[https://www . geesforgeks . org/optionaldouble-or else throw-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-orelsethrow-method-in-java-with-examples/)

**optionalduble**帮助我们创建一个可能包含也可能不包含 Double 值的对象。**or lsethrow()**方法帮助我们获得了双精度值。如果不存在双精度值，那么这个方法将抛出 NoSuchElemenrException。

**语法:**

```java
public Double orElseThrow()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个 OptionalDouble 描述的 Double 值。

**异常:**如果不存在值，该方法抛出 **NoSuchElementException**

下面的程序举例说明了 orElseThrow()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.orElseThrow() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble
            = OptionalDouble.of(134.1);

        // get value using orElseThrow()
        System.out.println("double Value extracted using"
                           + " orElseThrow() = "
                           + opDouble.orElseThrow());
    }
}
```

**输出**:

```java
double Value extracted using orElseThrow() = 134.1

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalDouble.orElseThrow() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble
            = OptionalDouble.empty();

        try {

            // try to get value from empty OptionalDouble
            Double value = opDouble.orElseThrow();
        }
        catch (Exception e) {

            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出**:

```java
Exception thrown : java.util.NoSuchElementException: No value present

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # orelsthrow()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#orElseThrow())
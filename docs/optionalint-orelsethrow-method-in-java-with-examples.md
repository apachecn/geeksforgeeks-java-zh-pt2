# Java 中的 OptionalInt orElseThrow()方法，带示例

> 原文:[https://www . geesforgeks . org/optional int-or else throw-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-orelsethrow-method-in-java-with-examples/)

**选项链接**帮助我们创建一个可能包含也可能不包含整数值的对象。
方法帮助我们获取 int 值，如果 int 值不存在，这个方法将抛出 NoSuchElemenrException。

**语法:**

```
public Int orElseThrow()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个选项描述的 Int 值。

**异常:**如果不存在值，该方法抛出 **NoSuchElementException**

下面的程序举例说明了 orElseThrow()方法:
**程序 1:**

```
// Java program to demonstrate
// OptionalInt.orElseThrow() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt = OptionalInt.of(12345);

        // get value using orElseThrow()
        System.out.println("int Value extracted using"
                           + " orElseThrow() = "
                           + opInt.orElseThrow());
    }
}
```

**输出**:

```
int Value extracted using orElseThrow() = 12345

```

**程序 2:**

```
// Java program to demonstrate
// OptionalInt.orElseThrow() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt = OptionalInt.empty();

        try {

            // try to get value from empty OptionalInt
            int value = opInt.orElseThrow();
        }
        catch (Exception e) {

            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出**:

```
Exception thrown : java.util.NoSuchElementException: No value present

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # orelsthrow()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#orElseThrow())
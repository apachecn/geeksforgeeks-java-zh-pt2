# Java 中的 OptionalLong orElseThrow()方法，带示例

> 原文:[https://www . geesforgeks . org/optional long-or else throw-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-orelsethrow-method-in-java-with-examples/)

**选项龙**帮助我们创建一个可能包含也可能不包含长值的对象。
**or else throw()**方法帮助我们获取值，如果值不存在，那么这个方法将抛出 NoSuchElemenrException。

**语法:**

```java
public Long orElseThrow()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该选项描述的 Long 值。

**异常:**如果不存在值，该方法抛出 **NoSuchElementException**

下面的程序举例说明了 orElseThrow()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalLong.orElseThrow() method
import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong opLong = OptionalLong.of(45213246);

        // get value using orElseThrow()
        System.out.println("Value extracted using"
                           + " orElseThrow() = "
                           + opLong.orElseThrow());
    }
}
```

**输出**:

```java
Value extracted using orElseThrow() = 45213246

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalLong.orElseThrow() method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong opLong = OptionalLong.empty();

        try {

            // try to get value from empty OptionalLong
            long value = opLong.orElseThrow();
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

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # orelsthrow()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#orElseThrow())
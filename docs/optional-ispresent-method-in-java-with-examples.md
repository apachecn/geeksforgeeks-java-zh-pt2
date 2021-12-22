# Java 中可选的 isPresent()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-is present-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-ispresent-method-in-java-with-examples/)

**是**的**法。Java 中的可选类**用于找出这个可选实例中是否存在值。如果此可选实例中没有值，则此方法返回 false，否则返回 true。

**语法:**

```
public boolean isPresent()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个**布尔**值，说明该可选实例中是否存在值。

下面的程序说明了 isPresent()方法:
**程序 1:**

```
// Java program to demonstrate
// Optional.isPresent() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.of(9455);

        // print value
        System.out.println("Optional: "
                           + op);

        // check for the value
        System.out.println("Is any value present: "
                           + op.isPresent());
    }
}
```

**Output:**

```
Optional: Optional[9455]
Is any value present: true

```

**程序 2:**

```
// Java program to demonstrate
// Optional.isPresent() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.empty();

        // print value
        System.out.println("Optional: "
                           + op);

        try {

            // check for the value
            System.out.println("Is any value present: "
                               + op.isPresent());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Optional: Optional.empty
Is any value present: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # isPresent–](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#isPresent--)
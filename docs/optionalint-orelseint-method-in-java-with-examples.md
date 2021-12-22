# Java 中的 option alint or LSE(int)方法，示例

> 原文:[https://www . geesforgeks . org/optional int-orelseint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-orelseint-method-in-java-with-examples/)

**or LSE(int)**方法帮助我们获取这个 OptionalInt 对象中的值。如果该选项中没有值，则该方法返回作为参数传递的值。

**语法:**

```java
public int orElse(int other)

```

**参数:**如果没有值，该方法接受 int 作为返回值。

**返回值:**该方法返回值，如果存在，否则为其他。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalInt.orElse(int) method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt = OptionalInt.of(452146);

        // get value using orElse
        int value = opInt.orElse(13421);

        // print value
        System.out.println("value: " + value);
    }
}
```

**Output:**

```java
value: 452146

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalInt.orElse(int) method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opInt = OptionalInt.empty();

        // get value using orElse
        int value = opInt.orElse(13421);

        // print value
        System.out.println("value: " + value);
    }
}
```

**Output:**

```java
value: 13421

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # orElse(int)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#orElse(int))
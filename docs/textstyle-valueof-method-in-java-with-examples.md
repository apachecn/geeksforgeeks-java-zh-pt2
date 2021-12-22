# Java 中 TextStyle valueOf()方法示例

> 原文:[https://www . geesforgeks . org/textstyle-value of-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/textstyle-valueof-method-in-java-with-examples/)

**文本样式枚举**的 **valueOf()** 方法用于返回具有指定名称的该类型文本样式的枚举。

**语法:**

```
public static TextStyle valueOf(String name)

```

**参数:**该方法接受**名称**作为参数，该参数是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的枚举常量。

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException** :如果这个枚举类型没有指定名称的常量。
*   **NullPointRexception**:如果参数为空。

下面的程序说明了 TextStyle.valueOf()方法:
**程序 1:**

```
// Java program to demonstrate
// TextStyle.valueOf() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle ts
            = TextStyle.valueOf("NARROW_STANDALONE");

        // print
        System.out.println("TextStyle: "
                           + ts);
    }
}
```

**Output:**

```
TextStyle: NARROW_STANDALONE

```

**程序 2:**

```
// Java program to demonstrate
// TextStyle.valueOf() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle ts
            = TextStyle.valueOf("SHORT_STANDALONE");

        // print
        System.out.println("TextStyle: "
                           + ts);
    }
}
```

**Output:**

```
TextStyle: SHORT_STANDALONE

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/textstyle . html # value of(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/time/format/TextStyle.html#valueOf(java.lang.String))
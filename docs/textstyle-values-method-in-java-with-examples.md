# Java 中的 TextStyle values()方法，示例

> 原文:[https://www . geesforgeks . org/textstyle-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/textstyle-values-method-in-java-with-examples/)

**TextStyle 枚举**的 **values()** 方法用于包含该枚举类型的常量的数组，按照它们被声明的顺序。

**语法:**

```
public static TextStyle[] values()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个包含这个枚举类型的常量的**数组**，按照它们被声明的顺序。

下面的程序说明了 TextStyle.values()方法:
**程序 1:**

```
// Java program to demonstrate
// TextStyle.values() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle ts
            = TextStyle.valueOf("NARROW");

        // apply values()
        TextStyle[] array
            = ts.values();

        // print
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**Output:**

```
FULL
FULL_STANDALONE
SHORT
SHORT_STANDALONE
NARROW
NARROW_STANDALONE

```

**程序 2:**

```
// Java program to demonstrate
// TextStyle.values() method
import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle ts
            = TextStyle.valueOf(
                "FULL_STANDALONE");

        // apply values()
        TextStyle[] array
            = ts.values();

        // print
        System.out.println(
            "TextStyle length:"
            + array.length);
    }
}
```

**Output:**

```
TextStyle length:6

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/textstyle . html # values()](https://docs.oracle.com/javase/10/docs/api/java/time/format/TextStyle.html#values())
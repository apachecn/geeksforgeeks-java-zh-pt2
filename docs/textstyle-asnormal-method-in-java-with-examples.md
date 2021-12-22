# Java 中的 TextStyle asNormal()方法，示例

> 原文:[https://www . geesforgeks . org/text style-as normal-in-Java-method-with-examples/](https://www.geeksforgeeks.org/textstyle-asnormal-method-in-java-with-examples/)

**TextStyle 枚举**的 **asNormal()** 方法用于返回与该 TextStyle 对象大小相同的正常样式。

**语法:**

```
public TextStyle asNormal()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回相同大小的普通样式。

下面的程序说明了 TextStyle.asNormal()方法:
**程序 1:**

```
// Java program to demonstrate
// TextStyle.asNormal() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle style
            = TextStyle.valueOf("SHORT_STANDALONE");

        // apply asNormal()
        TextStyle asNormalAttribute
            = style.asNormal();

        // print
        System.out.println(
            "Normal TextStyle :"
            + asNormalAttribute);
    }
}
```

**Output:**

```
Normal TextStyle :SHORT

```

**程序 2:**

```
// Java program to demonstrate
// TextStyle.asNormal() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle style
            = TextStyle.valueOf("FULL_STANDALONE");

        // apply asNormal()
        TextStyle asNormalAttribute
            = style.asNormal();

        // print
        System.out.println("Normal TextStyle :"
                           + asNormalAttribute);
    }
}
```

**Output:**

```
Normal TextStyle :FULL

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/textstyle . html # AsNormal()](https://docs.oracle.com/javase/10/docs/api/java/time/format/TextStyle.html#asNormal())
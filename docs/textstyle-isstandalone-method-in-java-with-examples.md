# TextStyle 是 Java 中的 stand only()方法，带有示例

> 原文:[https://www . geesforgeks . org/textstyle-is stand only-method-in-Java-with-examples/](https://www.geeksforgeeks.org/textstyle-isstandalone-method-in-java-with-examples/)

如果文本样式是独立样式，则使用**文本样式枚举**的**is stand only()**方法返回 true。

**语法:**

```
public TextStyle isStandalone()

```

**参数:**此方法不接受任何内容。

**返回值:**如果样式是独立样式，则此方法返回 **true** 。

下面的程序说明了 TextStyle.isStandalone()方法:
**程序 1:**

```
// Java program to demonstrate
// TextStyle.isStandalone() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle style
            = TextStyle.valueOf(
                "SHORT_STANDALONE");

        // apply isStandalone()
        boolean isStandaloneAttribute
            = style.isStandalone();

        // print
        System.out.println(
            "TextStyle is Standalone:"
            + isStandaloneAttribute);
    }
}
```

**Output:**

```
TextStyle is Standalone:true

```

**程序 2:**

```
// Java program to demonstrate
// TextStyle.isStandalone() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle style
            = TextStyle.valueOf("FULL");

        // apply isStandalone()
        boolean isStandaloneAttribute
            = style.isStandalone();

        // print
        System.out.println(
            "TextStyle is Standalone:"
            + isStandaloneAttribute);
    }
}
```

**Output:**

```
TextStyle is Standalone:false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/textstyle . html # isstandoll()](https://docs.oracle.com/javase/10/docs/api/java/time/format/TextStyle.html#isStandalone())
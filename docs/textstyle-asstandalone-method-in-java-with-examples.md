# Java 中的 TextStyle asStandalone()方法，带示例

> 原文:[https://www . geesforgeks . org/textstyle-as stand only-method-in-Java-with-examples/](https://www.geeksforgeeks.org/textstyle-asstandalone-method-in-java-with-examples/)

**TextStyle 枚举**的**as stand only()**方法用于返回与该 TextStyle 对象大小相同的单机样式。

**语法:**

```java
public TextStyle asStandalone()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回相同大小的**单机风格**。

下面的程序说明了 textstyle . as stand only()方法:
**程序 1:**

```java
// Java program to demonstrate
// TextStyle.asStandalone() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle style
            = TextStyle.valueOf("SHORT");

        // apply asStandalone()
        TextStyle asStandaloneAttribute
            = style.asStandalone();

        // print
        System.out.println(
            "Standlone TextStyle :"
            + asStandaloneAttribute);
    }
}
```

**Output:**

```java
Standlone TextStyle :SHORT_STANDALONE

```

**程序 2:**

```java
// Java program to demonstrate
// TextStyle.asStandalone() method

import java.time.format.TextStyle;

public class GFG {
    public static void main(String[] args)
    {

        // get TextStyle
        TextStyle style
            = TextStyle.valueOf("FULL");

        // apply asStandalone()
        TextStyle asStandaloneAttribute
            = style.asStandalone();

        // print
        System.out.println("Standlone TextStyle :"
                           + asStandaloneAttribute);
    }
}
```

**Output:**

```java
Standlone TextStyle :FULL_STANDALONE

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/textstyle . html # as stand only()](https://docs.oracle.com/javase/10/docs/api/java/time/format/TextStyle.html#asStandalone())
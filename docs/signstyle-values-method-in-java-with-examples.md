# Java 中 SignStyle values()方法，示例

> 原文:[https://www . geesforgeks . org/sign style-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/signstyle-values-method-in-java-with-examples/)

**SignStyle 枚举**的**值()**方法用于包含该 SignStyle 的单位的数组，按照它们被声明的顺序。

**语法:**

```java
public static SignStyle[] values()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个包含这个枚举类型的常量的**数组，按照它们被声明的顺序。**

下面的程序说明了 SignStyle.values()方法:
**程序 1:**

```java
// Java program to demonstrate
// SignStyle.values() method

import java.time.format.SignStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get SignStyle instance
        SignStyle signStyle
            = SignStyle.valueOf("NEVER");

        // Get the contants using values()
        SignStyle[] array
            = signStyle.values();

        // Print the values
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**程序 2:**

```java
// Java program to demonstrate
// SignStyle.values() method

import java.time.format.SignStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get SignStyle instance
        SignStyle signStyle
            = SignStyle.valueOf("NEVER");

        // Get the contants using values()
        SignStyle[] array
            = signStyle.values();

        // Print the values
        System.out.println("SignStyle length: "
                           + array.length);
    }
}
```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/sign style . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/SignStyle.html)
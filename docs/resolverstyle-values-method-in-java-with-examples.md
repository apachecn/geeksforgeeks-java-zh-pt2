# Java 中的 ResolverStyle values()方法，带示例

> 原文:[https://www . geesforgeks . org/resolver style-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/resolverstyle-values-method-in-java-with-examples/)

**ResolverStyle 枚举**的**值()**方法用于包含该 ResolverStyle 的单位的数组，按照它们被声明的顺序。

**语法:**

```
public static ResolverStyle[] values()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个包含这个枚举类型的常量的**数组，按照它们被声明的顺序。**

以下程序说明了 ResolverStyle.values()方法:
**程序 1:**

```
// Java program to demonstrate
// ResolverStyle.values() method

import java.time.format.ResolverStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get ResolverStyle instance
        ResolverStyle resolverStyle
            = ResolverStyle.valueOf("SMART");

        // Get the contants using values()
        ResolverStyle[] array
            = resolverStyle.values();

        // Print the values
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**Output:**

```
STRICT
SMART
LENIENT

```

**程序 2:**

```
// Java program to demonstrate
// ResolverStyle.values() method

import java.time.format.ResolverStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get ResolverStyle instance
        ResolverStyle resolverStyle
            = ResolverStyle.valueOf("LINIENT");

        // Get the contants using values()
        ResolverStyle[] array
            = resolverStyle.values();

        // Print the values
        System.out.println("ResolverStyle length: "
                           + array.length);
    }
}
```

**Output:**

```
ResolverStyle length: 3

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/resolver style . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/ResolverStyle.html)
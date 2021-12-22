# Java 中的 Number.intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/number-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/number-intvalue-method-in-java-with-examples/)

**java . lang . number . int value()**是 Java 中的一个内置方法，它将指定数字的值作为 int 返回。这可能涉及舍入或截断。

**语法:**

```
public abstract int intValue()

```

**参数**:该方法不接受任何参数。

**返回值:**该方法返回转换为 int 类型后该对象表示的数值。

下面的程序说明了 Number.intValue()方法:

**程序 1:**

```
// java program to demonstrate
// Number.intValue() method
public class gfg {

    public static void main(String[] args)
    {

        // get a number as float
        Float x = new Float(456f);
        // print the value as int
        System.out.println(x.intValue());

        // get a number as double
        Double y = new Double(20);
        // print the value as int
        System.out.println(y.intValue());
    }
}
```

**Output:**

```
456
20

```

**程序 2:**

```
// java program to demonstrate
// Number.intValue() method

public class gfg {

    public static void main(String[] args)
    {

        // get a number as float
        Float x = new Float(56f);
        // print the value as int
        System.out.println(x.intValue());

        // get a number as double
        Double y = new Double(76.2);
        // print the value as int
        System.out.println(y.intValue());
    }
}
```

**Output:**

```
56
76

```
# Java 中的 Number.shortValue()方法，带示例

> 原文:[https://www . geesforgeks . org/number-short value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/number-shortvalue-method-in-java-with-examples/)

**java . lang . number . short value()**是 Java 中的一个内置方法，它返回转换为短数据类型的指定数字的值。这可能涉及舍入或截断。

**语法:**

```
public abstract short shortValue()

```

**参数**:该方法不接受任何参数。

**返回值:**该方法返回转换为 short 类型后该对象表示的数值。

下面的程序说明了 Number.shortValue()方法:

**程序 1:**

```
// java program that demonstrates
// Number.shortValue() method
public class gfg {

    public static void main(String[] args)
    {

        // get a number as float
        Float x = new Float(7854123456f);
        // print the value as short
        System.out.println(x.shortValue());

        // get a number as double
        Double y = new Double(98774856);
        // print the value as short
        System.out.println(y.shortValue());
    }
}
```

**输出:**

```
-1
12104

```

**程序 2:**

```
// java program that demonstrates
// Number.shortValue() method

public class gfg {

    public static void main(String[] args)
    {

        // get a number as float
        Float x = new Float(78f);
        // print the value as short
        System.out.println(x.shortValue());

        // get a number as double
        Double y = new Double(56.23);
        // print the value as short
        System.out.println(y.shortValue());
    }
}
```

**输出:**

```
78
56

```
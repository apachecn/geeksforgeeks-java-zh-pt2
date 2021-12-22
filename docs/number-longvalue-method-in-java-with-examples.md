# Java 中的 Number.longValue()方法，带示例

> 原文:[https://www . geesforgeks . org/number-long value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/number-longvalue-method-in-java-with-examples/)

**java . lang . number . long value()**是 Java 中的一个内置方法，它返回转换为长数据类型的指定数字的值。这可能涉及舍入或截断。

**语法:**

```
public abstract long longValue()

```

**参数**:该方法不接受任何参数。

**返回值:**该方法返回转换为 long 类型后该对象表示的数值。

下面的程序说明了 Number.longValue()方法:

**程序 1:**

```
// java program to demonstrate
// Number.longValue() method
public class gfg {

    public static void main(String[] args)
    {

        // number as float
        Float x = new Float(127483456f);
        // print the value as long
        System.out.println(x.longValue());

        // number as double
        Double y = new Double(78549876);
        // print the value as long
        System.out.println(y.longValue());
    }
}
```

**Output:**

```
127483456
78549876

```

**程序 2:**

```
// java program to demonstrate
// Number.longValue() method
public class gfg {

    public static void main(String[] args)
    {

        // number as float
        Float x = new Float(127f);
        // print the value as long
        System.out.println(x.longValue());

        // number as double
        Double y = new Double(76.23);
        // print the value as long
        System.out.println(y.longValue());
    }
}
```

**Output:**

```
127
76

```
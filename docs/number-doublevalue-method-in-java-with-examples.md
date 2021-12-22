# Java 中的 Number.doubleValue()方法，带示例

> 原文:[https://www . geesforgeks . org/number-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/number-doublevalue-method-in-java-with-examples/)

**java . lang . number . Double VaLue()**是 Java 中的一个内置方法，它返回作为双数据类型的指定数字的值。这可能涉及舍入或截断。

**语法:**

```
public abstract double doubleValue()

```

**参数**:该方法不接受任何参数。

**返回值:**该方法返回转换为 double 类型后该对象表示的数值。

下面的程序说明了 Number.doubleValue()方法:

**程序 1:**

```
// java program that demonstrates
// the Number.doubleValue()
public class gfg {

    public static void main(String[] args)
    {

        // number as integer
        Integer x = new Integer(1234785456);
        // print value as double
        System.out.println(x.doubleValue());

        // number as float
        Float y = new Float(98745876f);
        // print value as double
        System.out.println(y.doubleValue());
    }
}
```

**Output:**

```
1.234785456E9
9.8745872E7

```

**程序 2:**

```
// java program that demonstrates
// the Number.doubleValue()

public class gfg {

    public static void main(String[] args)
    {

        // number as integer
        Integer x = new Integer(123);
        // print value as double
        System.out.println(x.doubleValue());

        // number as float
        Float y = new Float(9876f);
        // print value as double
        System.out.println(y.doubleValue());
    }
}
```

**Output:**

```
123.0
9876.0

```
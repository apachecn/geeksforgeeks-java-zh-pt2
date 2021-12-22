# Java 中的 Number.floatValue()方法，带示例

> 原文:[https://www . geesforgeks . org/number-float value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/number-floatvalue-method-in-java-with-examples/)

**java . lang . number . float value()**是 Java 中的一个内置方法，它返回转换为 float 数据类型的指定数字的值。这可能涉及舍入或截断。

**语法:**

```java
public abstract float floatValue()

```

**参数**:该方法不接受任何参数。

**返回:**该方法返回转换为类型 float 后该对象表示的数值。

下面的程序说明了 Number.floatValue()方法:

**程序 1:**

```java
// Below program demonstrate the
// Number.floatValue() method
public class gfg {

    public static void main(String[] args)
    {

        // number with integer datatype
        Integer x = new Integer(1785423456);
        // print the value as float
        System.out.println(x.floatValue());

        // number with double datatype
        Double y = new Double(97854876);
        // print the value as float
        System.out.println(y.floatValue());
    }
}
```

**Output:**

```java
1.78542349E9
9.785488E7

```

**程序 2:**

```java
// Below program demonstrate the
// Number.floatValue() method

public class gfg {

    public static void main(String[] args)
    {

        // number with integer datatype
        Integer x = new Integer(456);
        // print the value as float
        System.out.println(x.floatValue());

        // number with double datatype
        Double y = new Double(96);
        // print the value as float
        System.out.println(y.floatValue());
    }
}
```

**Output:**

```java
456.0
96.0

```
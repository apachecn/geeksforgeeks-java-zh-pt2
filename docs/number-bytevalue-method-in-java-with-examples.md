# Java 中的 Number.byteValue()方法，带示例

> 原文:[https://www . geesforgeks . org/number-byteevalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/number-bytevalue-method-in-java-with-examples/)

**java . lang . number . Bytevalue()**是 Java 中的一个内置方法，它以字节形式返回指定数字的值。这可能涉及舍入或截断。

**语法:**

```
public byte byteValue()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回转换为类型字节后该对象表示的数值。

下面的程序说明了 Number.byteValue()方法的使用:

**程序 1:**

```
// Java program to illustrate the
// Number.byteValue() method
public class gfg {

    public static void main(String[] args)
    {

        // Get a number as integer
        Integer x = new Integer(12345786);

        // Print bytevalue()
        System.out.println(x.byteValue());

        // Get a number as float
        Float y = new Float(9145876f);

        // Print bytevalue()
        System.out.println(y.byteValue());
    }
}
```

**Output:**

```
-70
20

```

**程序 2:**

```
// Java program to illustrate the
// Number.byteValue() method
public class gfg {

    public static void main(String[] args)
    {

        // Get a number as integer
        Integer x = new Integer(123);

        // Print  bytevalue()
        System.out.println(x.byteValue());

        // Get a number as float
        Float y = new Float(76f);

        // Print  bytevalue()
        System.out.println(y.byteValue());
    }
}
```

**Output:**

```
123
76

```
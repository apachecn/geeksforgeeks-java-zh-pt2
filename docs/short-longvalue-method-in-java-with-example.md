# Java 中的短 longValue()方法，示例

> 原文:[https://www . geesforgeks . org/short-long-value-in-Java-method-with-example/](https://www.geeksforgeeks.org/short-longvalue-method-in-java-with-example/)

[Short](https://www.geeksforgeeks.org/java-lang-short-class-java/)类的**java . lang . Short . long value()**方法是 Java 中的内置方法，用于将 Short 对象的值作为 long 返回。

**语法**

```
ShortObject.longValue()
```

**返回值:**返回短对象的值为**长**。

下面是 longValue()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Short longValue() method

class GFG {
    public static void main(String[] args)
    {

        // Short value
        Short a = 17;

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(a);

        // longValue of the Short Object
        long output = b.longValue();

        // printing the output
        System.out.println("Long value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Long value of 17 is : 17

```

**例 2:**

```
// Java code to demonstrate
// Short longValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(value);

        // longValue of the Short Object
        long output = b.longValue();

        // printing the output
        System.out.println("Long value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Long value of 17 is : 17

```
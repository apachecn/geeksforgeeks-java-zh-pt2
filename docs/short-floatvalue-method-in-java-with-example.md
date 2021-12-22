# Java 中的短浮点值()方法，示例

> 原文:[https://www . geesforgeks . org/short-float value-in-Java-method-with-example/](https://www.geeksforgeeks.org/short-floatvalue-method-in-java-with-example/)

[Short](https://www.geeksforgeeks.org/java-lang-short-class-java/) 类的**java . lang . Short . float value()**方法是 Java 中的一个内置方法，用于将 Short 对象的值作为 float 返回。

**语法:**

```java
public float floatValue()
```

**返回类型:**返回短对象的值为**浮动**。

下面是 floatValue()方法在 Java 中的实现:

**例 1:**

```java
// Java code to demonstrate
// Short floatValue() method

class GFG {
    public static void main(String[] args)
    {

        // Short value
        Short a = 17;

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(a);

        // floatValue of the Short Object
        float output = b.floatValue();

        // printing the output
        System.out.println("Float value of "
                           + a + " is : " + output);
    }
}
```

**Output:**

```java
Float value of 17 is : 17.0

```

**例 2:**

```java
// Java code to demonstrate
// Short floatValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(value);

        // floatValue of the Short Object
        float output = b.floatValue();

        // printing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Float value of 17 is : 17.0

```
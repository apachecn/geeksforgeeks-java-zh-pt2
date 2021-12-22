# Java 中的短 doubleValue()方法，示例

> 原文:[https://www . geesforgeks . org/short-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/short-doublevalue-method-in-java-with-examples/)

[Short](https://www.geeksforgeeks.org/java-lang-short-class-java/) 类的**java . lang . Short . Double VaLue()**方法是 Java 中的一个内置方法，用于将 Short 对象的值作为双精度返回。

**语法:**

```java
public double doubleValue()
```

**返回类型:**返回短对象的值为**双**。

下面是 doubleValue()方法在 Java 中的实现:

**例 1:**

```java
// Java code to demonstrate
// Short doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        // Short value
        Short a = 17;

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(a);

        // doubleValue of the Short Object
        double output = b.doubleValue();

        // printing the output
        System.out.println("Double value of "
                           + a + " is : " + output);
    }
}
```

**Output:**

```java
Double value of 17 is : 17.0

```

**例 2:**

```java
// Java code to demonstrate
// Short doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(value);

        // doubleValue of the Short Object
        double output = b.doubleValue();

        // printing the output
        System.out.println("Double value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Double value of 17 is : 17.0

```
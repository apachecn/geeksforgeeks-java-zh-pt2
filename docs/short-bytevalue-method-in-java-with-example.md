# Java 中的短字节赋值()方法，示例

> 原文:[https://www . geesforgeks . org/short-byteevalue-method-in-Java-with-example/](https://www.geeksforgeeks.org/short-bytevalue-method-in-java-with-example/)

[Short](https://www.geeksforgeeks.org/java-lang-short-class-java/)类的**java . lang . Short . Bytevalue()**方法是 Java 中的内置方法，用于将 Short 对象的值作为字节返回。

**语法**

```
ShortObject.byteValue()
```

**返回值:**返回短对象的值为**字节**。

下面是 byteValue()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Short byteValue() method

class GFG {
    public static void main(String[] args)
    {

        // Short value
        Short a = 17;

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(a);

        // byteValue of the Short Object
        byte output = b.byteValue();

        // printing the output
        System.out.println("Byte value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Byte value of 17 is : 17

```

**例 2:**

```
// Java code to demonstrate
// Short byteValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the Short value
        // in the wrapper class Short
        Short b = new Short(value);

        // byteValue of the Short Object
        byte output = b.byteValue();

        // printing the output
        System.out.println("Byte value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Byte value of 17 is : 17

```
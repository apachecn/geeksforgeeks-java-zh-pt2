# Java 中的短 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/short-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/short-hashcode-method-in-java-with-examples/)

[短类](https://www.geeksforgeeks.org/java-lang-short-class-java/)的 **hashCode()** 方法是 Java 中的内置方法，用于返回 ShortObject 的哈希代码。

**注意:**hashCode()返回的值与 intValue()相同。

**语法**

```
ShortObject.hashCode()
```

**返回值:**返回一个 **int** 值，代表指定 Short 对象的 hashcode。

下面是 hashCode()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Short hashCode() method

class GFG {
    public static void main(String[] args)
    {

        String value = "74";

        // wrapping the short value
        // in the wrapper class Short
        Short b = new Short(value);

        // hashCode of the Short Object
        int output = b.hashCode();

        // printing the output
        System.out.println("HashCode of "
                           + b + " : " + output);
    }
}
```

**Output:**

```
HashCode of 74 : 74

```

**例 2:**

```
// Java code to demonstrate
// Short hashCode() method

class GFG {
    public static void main(String[] args)
    {

        String value = "-17";

        // wrapping the short value
        // in the wrapper class Short
        Short b = new Short(value);

        // hashCode of the Short Object
        int output = b.hashCode();

        // printing the output
        System.out.println("HashCode of "
                           + b + " : " + output);
    }
}
```

**Output:**

```
HashCode of -17 : -17

```
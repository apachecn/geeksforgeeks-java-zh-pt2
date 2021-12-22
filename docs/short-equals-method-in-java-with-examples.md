# Java 中的 Short equals()方法，示例

> 原文:[https://www . geesforgeks . org/short-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/short-equals-method-in-java-with-examples/)

[短类](https://www.geeksforgeeks.org/java-lang-short-class-java/)的 **equals()** 方法是 Java 中的一个内置方法，用于比较给定对象的等式和调用 **equals()** 方法的 Short 实例。

**语法**

```
ShortObject.equals(Object a)
```

**参数:**它以对象类型对象 **a** 作为输入，与调用**等于**方法的短对象的实例进行比较。

**返回值:**返回一个**布尔**值。如果“a”的值等于 ShortObject 的值，则返回 true。

下面是 equals()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Short equals() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Short object
        Short a = new Short("20");

        // creating a Short object
        Short b = new Short("20");

        // equals method in Short class
        boolean output = a.equals(b);

        // Printing the output
        System.out.println("Does " + a
                           + " equals " + b
                           + " : " + output);
    }
}
```

**Output:**

```
Does 20 equals 20 : true

```

**例 2:**

```
// Java code to demonstrate
// Short equals() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Short object
        Short a = new Short("2");

        // creating a Short object
        Short b = new Short("20");

        // equals method in Short class
        boolean output = a.equals(b);

        // Printing the output
        System.out.println("Does " + a
                           + " equals " + b
                           + " : " + output);
    }
}
```

**Output:**

```
Does 2 equals 20 : false

```
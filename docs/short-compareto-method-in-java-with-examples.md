# Java 中的短 compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/short-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/short-compareto-method-in-java-with-examples/)

[短类](https://www.geeksforgeeks.org/java-lang-Short-class-java/)的 **compareTo()** 方法是 Java 中的内置方法，用于对两个短对象进行数值比较。

**语法:**

```java
public int compareTo(Short otherShort)
```

**参数**:该方法接受一个强制参数 **otherShort** ，即待比较的 Short 对象。

**返回类型:**返回一个 **int** 值。它返回:

*   如果“otherShort”等于“thisShort”，则为 0，
*   正值“thisShort”小于“otherShort”，
*   负值' otherShort '大于' thisShort '

下面是 compareTo()方法在 Java 中的实现:
**示例 1:**

```java
// Java code to demonstrate
// Short compareTo() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Short object
        Short a = new Short("4");

        // creating a Short object
        Short b = new Short("4");

        // compareTo method in Short class
        int output = a.compareTo(b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 4 and 4 : 0

```

**例 2:**

```java
// Java code to demonstrate
// Short compareTo() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Short object
        Short a = new Short("4");

        // creating a Short object
        Short b = new Short("2");

        // compareTo method in Short class
        int output = a.compareTo(b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 4 and 2 : 2

```

**例 3:**

```java
// Java code to demonstrate
// Short compareTo() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Short object
        Short a = new Short("2");

        // creating a Short object
        Short b = new Short("4");

        // compareTo method in Short class
        int output = a.compareTo(b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 2 and 4 : -2

```
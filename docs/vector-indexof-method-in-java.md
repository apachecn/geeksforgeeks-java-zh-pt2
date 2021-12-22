# Java 中()方法的向量索引

> 原文:[https://www . geesforgeks . org/vector-indexof-method-in-Java/](https://www.geeksforgeeks.org/vector-indexof-method-in-java/)

**Java . util . vector . indexof(Object element)**方法用于检查和查找向量中特定元素的出现。如果元素存在，则返回该元素第一次出现的索引，否则，如果向量不包含该元素，则返回-1。

**语法:**

```java
Vector.indexOf(Object element)
```

**参数:**向量类型的元素，它是强制的，因为它指定了需要在向量中检查其出现的元素。

**返回值:**向量中元素第一次出现的索引或位置。否则，如果向量中不存在元素，它将返回 **-1** 。返回值是整数类型。

**例 1:**

## 爪哇

```java
// Java Program to illustrate indexOf() Method
// of Vector class

// Importing required classes
import java.util.*;

// Main class
// VectorDemo
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty Vector by creating object of
        // Vector class of string type
        Vector<String> vec_tor = new Vector<String>();

        // Adding elements in the Vector
        // using add() method
        vec_tor.add("Geeks");
        vec_tor.add("for");
        vec_tor.add("Geeks");
        vec_tor.add("10");
        vec_tor.add("20");

        // Print and display all elements in above vector
        // object
        System.out.println("Vector: " + vec_tor);

        // Print commands where we are returning the 1st
        // position of element in vector object using
        // indexOf() method
        System.out.println(
            "The first occurrence of Geeks is at index:"
            + vec_tor.indexOf("Geeks"));
        System.out.println(
            "The first occurrence of 10 is at index: "
            + vec_tor.indexOf("10"));
    }
}
```

**输出:**

```java
Vector: [Geeks, for, Geeks, 10, 20]
The first occurrence of Geeks is at index:0
The first occurrence of 10 is at index: 3
```

**输出解释:**这里我们在向量中插入了一些元素，其中几乎没有重复的元素。在上面的例子中，“极客”是向量类中唯一被重复的元素，所以我们返回了第一个出现在索引中的元素，所以我们返回了“0”，而如果这个元素没有被重复，那么它的索引将被返回。

**例 2:**

## Java

```java
// Java Program to illustrate indexOf() Method
// of Vector class

// Importing required classes
import java.util.*;

// Main class
// VectorDemo
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Adding elements in the Vector
        // using add() method
        vec_tor.add(1);
        vec_tor.add(2);
        vec_tor.add(3);
        vec_tor.add(1);
        vec_tor.add(5);

        // Print and display all elements of vector object
        System.out.println("Vector: " + vec_tor);

        // Returning the 1st position of an element
        // using indexOf() method

        // Print and display commands
        System.out.println("The first occurrence of 1 is at index : "+ vec_tor.indexOf(1));
        System.out.println("The first occurrence of 3 is at index : "+ vec_tor.indexOf(7));
    }
}
```

**输出**

```java
Vector: [1, 2, 3, 1, 5]
The first occurrence of 1 is at index : 0
The first occurrence of 3 is at index : -1
```

**输出解释:**正如我们在上面所做的，我们在字符串的情况下取整数，这里我们唯一不同的是绕过一个不存在的元素，然后将返回“-1”，因为在 java 中不存在任何负索引，所以我们通常分配-1。
# Java 中的 Vector addElement()方法

> 原文:[https://www . geesforgeks . org/vector-addelement-method-in-Java/](https://www.geeksforgeeks.org/vector-addelement-method-in-java/)

[](https://www.geeksforgeeks.org/java-util-vector-class-java/)****。addElement()** 方法用于通过将向量的大小增加 1 来将指定的元素追加到该向量的末尾。该方法的功能类似于 Vector 类的 **add()** 方法。
**语法:**** 

```java
boolean addElement(Object element)
```

****参数:**该函数接受对象类型的单个参数*元素*，并引用该参数指定的元素追加到向量的末尾。
**返回值:**这是一个 void 类型的方法，不返回值。
下面的程序说明了 Java . util . vector . add(Object element)方法的工作原理。
**程序 1 :**** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java code to illustrate boolean addElement()
import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements in the vector
        vec_tor.add("Geeks");
        vec_tor.add("for");
        vec_tor.add("Geeks");
        vec_tor.add("10");
        vec_tor.add("20");

        // Output the present vector
        System.out.println("The vector is: " + vec_tor);

        // Adding new elements to the end
        vec_tor.addElement("Last");
        vec_tor.addElement("Element");

        // Printing the new vector
        System.out.println("The new Vector is: " + vec_tor);
    }
}
```

****Output:** 

```java
The vector is: [Geeks, for, Geeks, 10, 20]
The new Vector is: [Geeks, for, Geeks, 10, 20, Last, Element]
```** 

****节目 2:**** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java code to illustrate boolean addElement()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements in the vector
        vec_tor.add(1);
        vec_tor.add(2);
        vec_tor.add(3);
        vec_tor.add(10);
        vec_tor.add(20);

        // Output the present vector
        System.out.println("The vector is: " + vec_tor);

        // Adding new elements to the end
        vec_tor.addElement(50);
        vec_tor.addElement(100);

        // Printing the new vector
        System.out.println("The new Vector is: " + vec_tor);
    }
}
```

****Output:** 

```java
The vector is: [1, 2, 3, 10, 20]
The new Vector is: [1, 2, 3, 10, 20, 50, 100]
```**
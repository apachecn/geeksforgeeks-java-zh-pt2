# Java 中的向量 copyInto()方法

> 原文:[https://www . geesforgeks . org/vector-copy into-method-in-Java/](https://www.geeksforgeeks.org/vector-copyinto-method-in-java/)

**Java . util . vector . copy into()**方法用于将该向量的所有分量复制到另一个数组中，该数组有足够的空间容纳该向量的所有分量。需要注意的是，元素的索引保持不变。数组中的元素被向量的元素替换。

**语法:**

```java
Vector.copyInto(Object array[])
```

**参数:**参数**数组[]** 为向量类型。这是向量元素要复制到的数组。

**返回值:**该方法为 **void** 类型，不返回值。

**异常:**如果数组为空，该方法抛出**空指针异常**。

下面的程序说明了 Java.util.Vector.copyInto()方法:

**程序 1:**

```java
// Java code to illustrate copyInto()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("4");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Creating an array
        String arr[] = new String[6];

        arr[0] = "Hello";
        arr[1] = "World";

        // Displaying the initial array
        System.out.println("The initial array is: ");
        for (String str : arr)
            System.out.println(str);

        // Copying
        vec_tor.copyInto(arr);

        // The final array
        System.out.println("The final array is: ");
        for (String str : arr)
            System.out.println(str);
    }
}
```

**Output:**

```java
Vector: [Welcome, To, Geeks, 4, Geeks]
The initial array is: 
Hello
World
null
null
null
null
The final array is: 
Welcome
To
Geeks
4
Geeks
null

```

**程序 2:**

```java
// Java code to illustrate copyInto()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements into the Vector
        vec_tor.add(10);
        vec_tor.add(20);
        vec_tor.add(30);
        vec_tor.add(40);
        vec_tor.add(50);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Creating an array
        Integer arr[] = new Integer[6];

        arr[0] = 50;
        arr[1] = 60;
        arr[2] = 70;
        arr[3] = 80;
        arr[4] = 90;

        // Displaying the initial array
        System.out.println("The initial array is: ");
        for (Integer str : arr)
            System.out.println(str);

        // Copying
        vec_tor.copyInto(arr);

        // The final array
        System.out.println("The final array is: ");
        for (Integer str : arr)
            System.out.println(str);
    }
}
```

**Output:**

```java
Vector: [10, 20, 30, 40, 50]
The initial array is: 
50
60
70
80
90
null
The final array is: 
10
20
30
40
50
null

```
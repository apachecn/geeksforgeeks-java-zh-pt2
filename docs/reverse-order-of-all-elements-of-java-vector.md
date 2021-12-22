# Java 向量所有元素的逆序

> 原文:[https://www . geesforgeks . org/Java-vector 所有元素的逆序/](https://www.geeksforgeeks.org/reverse-order-of-all-elements-of-java-vector/)

[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)实现动态数组意味着它可以根据需要收缩和扩展它的大小，就像在数组中有相同的操作一样。不要把它和[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)混淆，因为在向量和数组列表之间有一条细线，向量是同步的，两者的插入顺序保持不变。Vector 存在于 **java.util** 包中，实现了列表接口

**说明:**反转向量中元素的顺序

> 输入:[1，2，3，4，5]
> 
> 输出:[5，4，3，2，1]
> 
> 输入:[“极客”、“FOR”、“极客”]
> 
> 输出:[“极客”、“FOR”、“极客”]

**方法:**

1.  使用 for 循环(简单方法)
2.  使用 [*采集.*](https://www.geeksforgeeks.org/collections-reverse-java-examples/) 方法
3.  使用 [*列表迭代器()*](https://www.geeksforgeeks.org/vector-listiterator-method-in-java-with-examples/) 方法

**方法 1:** 使用 for 循环以相反的顺序打印向量的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print vector element
// in reverse using for loop

// Importing Vector, Collection & ListIterator classes
// and generic java input output class
import java.io.*;
import java.util.Vector;
import java.util.Collections;
import java.util.ListIterator;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating vector of integer
        Vector<Integer> v1 = new Vector<Integer>();

        // Adding element to vector
        // Custom inputs
        v1.add(1);
        v1.add(2);
        v1.add(3);
        v1.add(4);
        v1.add(5);

        // Display message
        System.out.println("Before reverse of vector : ");

        // Printing all elements of vector before reversing
        System.out.println(v1);

        // Display message
        System.out.println("After reverse of vector : ");

        // Iterating from last index of vector to 0
        // index = vector.size()-1 (last index)
        for (int i = v1.size() - 1; i >= 0; i--) {

            // Printing elements of vector after reversing
            System.out.println(v1.get(i));
        }
    }
}
```

**Output**

```
Before reverse of vector : 
[1, 2, 3, 4, 5]
After reverse of vector : 
5
4
3
2
1
```

时间复杂度:**n 次的 O(n)，其中 n 是向量中的元素个数。**

****方法二:** [Collection.reverse()](https://www.geeksforgeeks.org/collections-reverse-java-examples/) 方法顾名思义就是 Collection 类的一种方法。**

****语法:****

```
Collections.reverse(vector) ;
```

****参数:**要反转的矢量对象**

****返回值:**返回向量元素的逆序。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to reverse order of elements of vector

// Importing generic java input/output classes
import java.io.*;

// Importing Vector and Collection class
// from java.util package
import java.util.Vector;
import java.util.Collections;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create a Vector object
        Vector<String> v = new Vector<String>();

        // Add elements to Vector
        v.add("GFG");
        v.add("EarlierGreen");
        v.add("NowBlack");

        // Display vector element before reversing
        System.out.println(
            "Before Reverse Order, Vector Contains : " + v);

        // reverse() method to reverse vector element
        // by passing vector object so as to reverse
        Collections.reverse(v);

        // Display vector element after reversing
        System.out.println(
            "After Reverse Order, Vector Contains : " + v);
    }
}
```

****Output**

```
Before Reverse Order, Vector Contains : [GFG, EarlierGreen, NowBlack]
After Reverse Order, Vector Contains : [NowBlack, EarlierGreen, GFG]
```** 

****方法 3:** 使用 [*列表迭代器()*](https://www.geeksforgeeks.org/vector-listiterator-method-in-java-with-examples/) 方法**

****语法:****

```
public ListIterator listIterator()
```

****参数:**该方法不接受输入参数。**

****返回值:**这个方法返回一个[列表迭代器](https://www.geeksforgeeks.org/iterators-in-java/#ListIterator)对象，可以用来遍历 Vector 对象。该对象可用于遍历矢量对象。它是双向的，所以向前和向后遍历都是可能的，分别使用 *next()* 和 *previous()* 。**

****返回类型:**列表迭代器**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to reverse order of elements of vector
// using listiterator

// Importing Vector and ListIterator classes
// of java.util package
import java.util.Vector;
import java.util.ListIterator;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create(Declare) empty vector
        Vector<String> v1 = new Vector<String>();

        // Add elements to vector using add() method
        v1.add("Geeks");
        v1.add("for");
        v1.add("Geeks");
        v1.add("is");
        v1.add("Best");

        // Print message
        System.out.print("Before: ");

        // Printing all elements of Vector before reversing
        System.out.println(v1);

        // Declare list iterator
        ListIterator<String> l_itr
            = v1.listIterator(v1.size());

        // Iistiterator to reverse the vector element using
        // hashPrevious() method

      // Print message
        System.out.println("After: ");

        while (l_itr.hasPrevious())

          // Print vector elements after reversing
            System.out.println(l_itr.previous());
    }
}
```

****Output**

```
Before: [Geeks, for, Geeks, is, Best]
After: 
Best
is
Geeks
for
Geeks
```**
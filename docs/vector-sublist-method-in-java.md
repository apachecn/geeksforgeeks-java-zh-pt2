# Java 中的 Vector subList()方法

> 原文:[https://www . geesforgeks . org/vector-sublist-method-in-Java/](https://www.geeksforgeeks.org/vector-sublist-method-in-java/)

**Java . util . Vector . sublist()**用于返回参数中提到的范围内现有 Vector 的子列表。该方法接受一个上限和一个下限，并返回该范围内提到的所有元素。如果列表中存在元素，则包括下限，排除上限。基本上，它接受大于等于下限且严格小于上限的子列表元素。

**语法:**

```
Vector.subList(int low_index, int up_index)
```

**参数:**该方法接受 2 个强制参数:

*   **low_index:** 这是整数类型，定义了计算子列表的起始元素的下限或索引。这个元素是子列表中包含的**。**
*   ****up_index:** 这是整数类型，定义了结束元素的上限或索引，直到计算子列表。这个元素被**从子列表中排除了**。**

****返回值:**该方法返回给定参数范围内提到的向量类型的**子列表**。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate subList() method
// of Vector class

// Importing required class
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty Vector by declaring
        // object of Vector class of Integer type
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Adding custom input elements
        // using add() method
        vec_tor.add(5);
        vec_tor.add(1);
        vec_tor.add(50);
        vec_tor.add(10);
        vec_tor.add(20);
        vec_tor.add(6);
        vec_tor.add(20);
        vec_tor.add(18);
        vec_tor.add(9);
        vec_tor.add(30);

        // Print and display all elements present in vector
        System.out.println("The Vector is: " + vec_tor);

        // Creating the sublist vector
        List<Integer> sub_list = new ArrayList<Integer>();

        // Limiting the values till 5
        // using subList() method via passing arguments
        sub_list = vec_tor.subList(2, 5);

        // Displaying the elements present inside list
        System.out.println("The resultant values "
                           + "within the sub list: "
                           + sub_list);
    }
}
```

****Output:** 

```
The Vector is: [5, 1, 50, 10, 20, 6, 20, 18, 9, 30]
The resultant values within the sub list: [50, 10, 20]
```** 

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate subList() method
// of Vector class

// Importing required class
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty Vector by
        // creating string object of Vector class
        Vector<String> vec_tor = new Vector<String>();

        // Adding custom input elements to above vector
        // object using add() method
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geek");
        vec_tor.add("For");
        vec_tor.add("Geeks");

        // Display message only
        System.out.println("The Vector is: " + vec_tor);

        // Creating the sublist vector
        List<String> sub_list = new ArrayList<String>();

        // Limiting the values till 5
        // using subList() method
        sub_list = vec_tor.subList(1, 5);

        // Display elements of List object
        System.out.println("The resultant values "
                           + "within the sub list: "
                           + sub_list);
    }
}
```

****Output**

```
The Vector is: [Welcome, To, Geek, For, Geeks]
The resultant values within the sub list: [To, Geek, For, Geeks]
```**
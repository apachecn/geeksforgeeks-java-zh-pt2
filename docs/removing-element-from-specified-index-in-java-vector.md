# 从 Java 向量的指定索引中移除元素

> 原文:[https://www . geesforgeks . org/remove-element-from-specified-index-in-Java-vector/](https://www.geeksforgeeks.org/removing-element-from-specified-index-in-java-vector/)

Java 向量中指定索引处的元素可以使用 [**remove()**](https://www.geeksforgeeks.org/remove-element-arraylist-java/) 方法移除。这个方法存在于 java.util.Vector 类中。我们可以传递将作为参数移除的元素的索引。remove()方法 return 方法返回被移除的元素。

**语法:**

```
public removed_element remove(int index)
```

**参数:**要移除的元素的索引。

**返回类型:**该方法返回从列表中删除的元素。

**异常:**如果指数超出范围，该方法抛出**指数。**

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for removing element
// at specified index

import java.util.Vector;
public class GFG {
    public static void main(String arg[])
    {
        // Create an Vector
        Vector<Integer> vector = new Vector<>();

        // Add elements in the vector
        vector.add(10);
        vector.add(20);
        vector.add(30);
        vector.add(20);
        vector.add(40);

        // display original vector
        System.out.println("Values in vector: " + vector);

        // remove 2 index element and store the value in r
        int r = vector.remove((2));

        // display removed element
        System.out.println("Removed element: " + r);

        // display vector after 2 index element
        System.out.println("Values in vector: " + vector);
    }
}
```

**Output**

```
Values in vector: [10, 20, 30, 20, 40]
Removed element: 30
Values in vector: [10, 20, 20, 40]

```

**remove()方法异常:**

当我们试图移除索引处大于或等于数组列表大小的元素时，编辑器会在运行时给出 **IndexOutOfBound 异常** 。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show the exception 
// of remove() method 

import java.util.ArrayList; 

public class ArrayListDemo { 
   public static void main(String[] args) { 

      // create an empty array list with an initial capacity 
      ArrayList<Integer> arrlist = new ArrayList<Integer>(5); 

      // use add() method to add elements in the deque 
      arrlist.add(26); 
      arrlist.add(18); 
      arrlist.add(31); 
      arrlist.add(42); 

      System.out.println("Size of list: " + arrlist.size()); 

      // let us print all the elements available in list 
      for (Integer number : arrlist) { 
         System.out.println("Number = " + number); 
      }   

      // Removes element at 5th position 
      // which is not present in the list 
      // and will therefore give IndexOutOfBound exception 
      arrlist.remove(4); 

      System.out.println("Now, Size of list: " + arrlist.size()); 

      // let us print all the elements available in list 
      for (Integer number : arrlist) { 
         System.out.println("Number = " + number); 
      } 
   } 
}
```

```
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index 4 out of bounds for length 4
```
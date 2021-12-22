# 从 Java 数组列表的指定索引中移除元素

> 原文:[https://www . geesforgeks . org/从指定的 java-arraylist 索引中移除元素/](https://www.geeksforgeeks.org/removing-element-from-the-specified-index-in-java-arraylist/)

java.util.ArrayList 类中的 **remove(int index)** 方法删除列表中指定位置的元素，并将任何后续元素向左移动(即从它们的索引中减去 1)。

**语法:**

```
public removed_element remove(int index)
```

**参数:**要移除的元素的索引。

**返回类型:**该方法返回从列表中删除的元素。

**异常:**如果指数超出范围，该方法抛出**指数。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove an element
// from an specified index from
// an ArrayList.

import java.util.ArrayList;

public class GFG {
    public static void main(String[] arg)
    {

        // creating an empty ArrayList with an initial
        // capacity of 5
        ArrayList<String> flower = new ArrayList<String>(5);

        // using add() method to add elements in the
        // ArrayList flower
        flower.add("red-rose");
        flower.add("tulip");
        flower.add("sun-flower");
        flower.add("marie-gold");
        flower.add("orchid");

        // printing the size of the ArrayList flower
        System.out.println("Size of list: "
                           + flower.size());

        // printing the ArrayList flower
        System.out.println("Flower ArrayList = " + flower);

        // Removing element at 3rd position from ArrayList
        // flower
        System.out.println(
            "Removing element at index = 2 ");
        flower.remove(2);

        System.out.println("After removing element");

        // printing the size of the ArrayList flower
        System.out.println("Size of list: "
                           + flower.size());

        // printing the ArrayList flower
        System.out.println("Flower ArrayList = " + flower);
    }
}
```

**Output**

```
Size of list: 5
Flower ArrayList = [red-rose, tulip, sun-flower, marie-gold, orchid]
Removing element at index = 2 
After removing element
Size of list: 4
Flower ArrayList = [red-rose, tulip, marie-gold, orchid]
```

当我们试图移除索引处大于或等于数组列表大小的元素时，编辑器会在运行时给出 **IndexOutOfBound 异常**。

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
      arrlist.add(20);
      arrlist.add(15);
      arrlist.add(30);
      arrlist.add(45);

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
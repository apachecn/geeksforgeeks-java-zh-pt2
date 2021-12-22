# 使用比较器

对 Java 向量进行降序排序

> 原文:[https://www . geesforgeks . org/sort-Java-vector-按降序-使用比较器/](https://www.geeksforgeeks.org/sort-java-vector-in-descending-order-using-comparator/)

**向量** 类实现了一个可增长的对象数组。向量基本上属于遗留类，但现在它与集合完全兼容。在 [**java.util 包**](https://www.geeksforgeeks.org/java-util-package-java/) 中找到，实现了 [列表](https://www.geeksforgeeks.org/list-interface-java-examples/) 界面，所以我们可以使用列表界面的所有方法。

**排序技术有两种:**

*   首先是内部排序，即使用预定义的排序方法升序 [Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 用于原始类数组和包装类数组， [Collections.sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/) 用于[集合](https://www.geeksforgeeks.org/collections-in-java-2/)这两种方法都以升序对元素进行排序。
*   第二种技术是传递比较器或者在类中实现[比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)作为两种方法中的第二个参数，并根据需求改变排序顺序。比较器只适用于包装类类型数组和集合，如 vector、ArrayList 等。

**输入:**

```java
vector [4,3,2,6,7]
```

**输出:**

```java
vector [2,3,4,6,7]
```

**使用比较器按降序排序** [**向量**](https://www.geeksforgeeks.org/java-util-vector-class-java/) **的方法:**

1.  在类中实现比较器接口，并更改元素的自然顺序
2.  在 **Collections.sort()** 方法的第二个参数中直接调用新的比较器，改变元素的顺序

**示例 1:** 在实现比较器类的类中重写比较方法，然后在调用 Collections.sort()方法时创建并传递该类的对象作为第二个参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Sort Java Vector in
// descending order using comparator

import java.io.*;
import java.util.*;

// Implement comparator of the Integer class
class GFG implements Comparator<Integer>
{
    // Function to print the elements of the vector
    static void print(Vector<Integer> Numbers)
    {
        for (Integer number : Numbers)
        {
            // Printing the elements
            System.out.print(number + " ");
        }
    }

    public static void main(String[] args)
    {
        // Implementing the vector class
        Vector<Integer> elements = new Vector<>();

        // Adding elements in the vector class
        elements.add(4);
        elements.add(3);
        elements.add(2);
        elements.add(6);
        elements.add(7);

        // Before sorting the elements
        System.out.print("Before sorting elements ");

        print(elements);

        System.out.println();

        // Sorting the vector elements in descending
        // order
        Collections.sort(elements, new GFG());

        System.out.print("After sorting elements ");

        // Printing the elements
        print(elements);
    }

    // Implementing compare function
    @Override public int compare(Integer o1, Integer o2)
    {
        // Changing the order of the elements
        return o2 - o1;
    }
}
```

**Output**

```java
Before sorting elements 4 3 2 6 7 
After sorting elements 7 6 4 3 2
```

**示例 2:** 在调用 Collections.sort()方法时覆盖比较函数本身。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Sort Java Vector in
// descending order using comparator

import java.io.*;
import java.util.*;

class GFG {

    // Function to print the elements of the vector
    static void print(Vector<Integer> Numbers)
    {
        for (Integer number : Numbers) {
            // Printing the elements
            System.out.print(number + " ");
        }
    }

    public static void main(String[] args)
    {
        // Implementing the vector class
        Vector<Integer> elements = new Vector<>();

        // Adding elements in the vector class
        elements.add(4);
        elements.add(3);
        elements.add(2);
        elements.add(6);
        elements.add(7);

        // Before sorting the elements
        System.out.print("Before sorting elements ");

        print(elements);
        System.out.println();

        // Sorting the vector elements in descending
        // order
        Collections.sort(
            elements, new Comparator<Integer>() {
                @Override
                public int compare(Integer o1, Integer o2)
                {
                    // Changing the order of the elements
                    return o2 - o1;
                }
            });

        System.out.print("After sorting elements ");

        // Printing the elements
        print(elements);
    }
}
```

**Output**

```java
Before sorting elements 4 3 2 6 7 
After sorting elements 7 6 4 3 2
```
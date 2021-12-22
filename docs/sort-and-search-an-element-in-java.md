# 在 Java 中排序和搜索元素

> 原文:[https://www . geesforgeks . org/sort-and-search-in-a-element-in-Java/](https://www.geeksforgeeks.org/sort-and-search-an-element-in-java/)

在 Java 中，对数组中的元素进行排序和搜索非常容易。与 C 语言不同，在 C 语言中，我们必须使所有的函数都工作，Java 有内置的函数来做同样的工作。要对数组进行排序，有一个排序函数；要在排序后的数组中搜索元素，有一个 binarySearch()函数。要了解这些功能的更多信息，请阅读以下文章:

**排序:** [数组. Java 中的 sort()示例](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)

**时间复杂度:** *O (n log n)*

**排序语法:**

```
Arrays.sort(array_name);

```

**搜索:**[Java 中的 Arrays.binarySearch()示例](https://www.geeksforgeeks.org/arrays-binarysearch-java-examples-set-1/)

对于使用二分搜索法数组必须事先排序

**要点:**

*   如果输入数组没有排序，结果是未定义的和负的。
*   如果有重复，不能保证会找到哪一个。

**时间复杂度:** *O (log n)*

**二进制搜索语法:**

```
Arrays.binarySearch(array_name, key);

```

我们总是可以创建用户定义的函数，但是 Java 中的内置函数已经在使用复杂度最低的算法，所以没有必要创建这样的函数。

**示例 1:** 在排序数组中查找元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find an 
// element in an sorted array

// Importing util files
import java.util.*;

public class Gfg {

    // Main function
    public static void main(String args[]) throws Exception
    {

        // Sorted Array
        int array[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Using binarySearch to search for desired element
        int index = Arrays.binarySearch(array, 2);

        // Printing result
        if (index >= 0)
            System.out.println("Element 2 found at index: "
                               + index);
        else
            System.out.println("Element not found");
    }
}
```

**输出:**

```
Element 2 found at index: 1

```

**示例 2:** 对数组进行排序，并在排序后的数组中搜索元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Sorting an array and
// searching for an element in the 
// sorted array

// Importing util files
import java.util.*;

public class Gfg {

    // Main function
    public static void main(String args[]) throws Exception
    {

        // Unsorted Array
        int array[] = { 10, 9, 8, 7, 6, 5, 4, 3, 2, 1 };

        // Sorting the array
        Arrays.sort(array);

        // Printing sorted array
        System.out.println("Sorted Array:");
        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }
        System.out.println();

        // Using binarySearch to search for desired element
        int index = Arrays.binarySearch(array, 0);

        // Printing result
        if (index >= 0)
            System.out.println("Element 2 found at index: "
                               + index);
        else
            System.out.println("Element not found");
    }
}
```

**输出:**

```
Sorted Array:
1 2 3 4 5 6 7 8 9 10 
Element 2 found at index: 1

```
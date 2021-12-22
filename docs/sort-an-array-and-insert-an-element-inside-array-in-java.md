# 在 Java 中对数组进行排序并在数组中插入元素

> 原文:[https://www . geesforgeks . org/sort-a-array-and-insert-a-element-in-array-in-Java/](https://www.geeksforgeeks.org/sort-an-array-and-insert-an-element-inside-array-in-java/)

对数组进行排序可以通过使用内置的排序函数来完成，而对于插入，我们必须创建一个新的数组来完成，因为 Java 中的数组是不可变的。要了解更多关于 Java 排序的信息，请阅读下面的文章:

**排序:**[Java 中的 Arrays.sort()示例](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)

**方法 1:**

1.  Create a new array of size N+1.
2.  The new array replicates the first array.
3.  Insert a number at the end of the array.
4.  Sort arrays.

**示例:**插入一个元素，然后对数组进行排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to insert an element in
// an array and then sorting it.

// Importing util files
import java.util.*;

public class Gfg {

    // Main function
    public static void main(String args[]) throws Exception
    {

        // Given number
        int given_number = 1;

        // Array
        int array[] = { 6, 7, 8, 2, 3, 4, 5, 9, 10 };

        // Creating new array with increased size
        int new_array[] = new int[array.length + 1];

        // Copying elements from one array to another
        for (int i = 0; i < array.length; i++) {
            new_array[i] = array[i];
        }

        // Adding new element
        new_array[new_array.length - 1] = given_number;

        // Sorting new array
        Arrays.sort(new_array);

        // print array
        for (int i = 0; i < new_array.length; i++)
            System.out.print(new_array[i] + " ");
    }
}
```

**Output**

```
1 2 3 4 5 6 7 8 9 10 
```

**时间复杂度:** O(n log n)

**进场 2:**

1.  Tidy up the situation.
2.  Create a new N+1 array.
3.  Begins traversing the given array and copying elements.
4.  If the given number is less than or equal to the number in the array, the given number is appended to the new array.
5.  Copies the remaining elements of a given array into a new array.

**示例:**插入一个元素，然后对数组进行排序。

## Java

```
// Java program to insert an element
// in an array and then sorting it.

// Importing util files
import java.util.*;

public class Gfg {

    // Main function
    public static void main(String args[]) throws Exception
    {

        // Given Number
        int given_number = 1;

        // Array
        int array[] = { 6, 7, 8, 2, 3, 4, 5, 9, 10 };

        // Sort Given array
        Arrays.sort(array);

        // Creating new array with increased size
        int new_array[] = new int[array.length + 1];

        // Copying elements from one
        // array to another as in approach 2
        int i = 0, j = 0;
        for (i = 0; i < new_array.length; i++) {
            if (given_number <= array[i]) {
                new_array[i] = given_number;
                break;
            }
            else
                new_array[i] = array[j++];
        }

        // copy the remaining elements
        for (int k = i + 1; k < new_array.length; k++)
            new_array[k] = array[j++];

        // print new array
        for (i = 0; i < new_array.length; i++)
            System.out.print(new_array[i] + " ");
    }
}
```

**输出**

```
1 2 3 4 5 6 7 8 9 10 
```

**时间复杂度:** O(n log n)

**方法 3:**

1.  Create a collection.
2.  Start adding all elements in the collection.
3.  Copies the remaining elements of the given collection into a new array.

**示例:**插入一个元素，然后对数组进行排序。

## Java

```
// Java program to insert an element
// in an array and then sorting it.

// Importing util files
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

public class GFG {

    public static void main(String[] args)
    {

        // using wrapper class here for array,
        // to convert into object
        Integer arr[] = { 6, 7, 8, 2, 3, 4, 5, 9, 10 };

        Set<Integer> sets
            = new HashSet<Integer>(Arrays.asList(arr));

        sets.add(1);

        arr = sets.toArray(arr);

        // print the array
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出**

```
1 2 3 4 5 6 7 8 9 10 
```

**时间复杂度:** O(n log n)
# 从 Java 中的数组中移除特定索引处的元素

> 原文:[https://www . geesforgeks . org/从 java 数组中移除特定于元素的索引/](https://www.geeksforgeeks.org/remove-an-element-at-specific-index-from-an-array-in-java/)

给定一个固定长度的数组。任务是从数组中移除特定索引处的元素。

**示例:**

```
Input: arr[] = { 1, 2, 3, 4, 5 }, index = 2
Output: arr[] = { 1, 2, 4, 5 }

Input: arr[] = { 4, 5, 9, 8, 1 }, index = 3
Output: arr[] = { 4, 5, 9, 1 }
```

数组是包含一组元素的数据结构。通常，这些元素都是相同的数据类型，如整数或字符串。数组通常在计算机程序中用于组织数据，以便可以快速对一组相关的值进行排序或搜索。数组的所有项目都存储在连续的内存位置。

### 方法

有许多方法可以检查这个数组中是否有特定的元素。这些是–

*   使用另一个数组
*   使用 [Java 8 流](https://www.geeksforgeeks.org/java-8-stream/)
*   使用[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)
*   使用 System.arraycopy()方法

### 1.使用另一个数组(简单或基本方法)

基本方法包括在指定的索引处找到元素，然后移除该元素。其余的元素被复制到一个新的数组中。这将导致数组的大小比原始数组小一。下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove an element
// from a specific index from an array

import java.util.Arrays;

class GFG {

    // Function to remove the element
    public static int[] removeTheElement(int[] arr, int index)
    {

        // If the array is empty
        // or the index is not in array range
        // return the original array
        if (arr == null || index < 0
            || index >= arr.length) {

            return arr;
        }

        // Create another array of size one less
        int[] anotherArray = new int[arr.length - 1];

        // Copy the elements except the index
        // from original array to the other array
        for (int i = 0, k = 0; i < arr.length; i++) {

            // if the index is
            // the removal element index
            if (i == index) {
                continue;
            }

            // if the index is not
            // the removal element index
            anotherArray[k++] = arr[i];
        }

        // return the resultant array
        return anotherArray;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Get the array
        int[] arr = { 1, 2, 3, 4, 5 };

        // Print the resultant array
        System.out.println("Original Array: "
                           + Arrays.toString(arr));

        // Get the specific index
        int index = 2;

        // Print the index
        System.out.println("Index to be removed: " + index);

        // Remove the element
        arr = removeTheElement(arr, index);

        // Print the resultant array
        System.out.println("Resultant Array: "
                           + Arrays.toString(arr));
    }
}
```

**Output**

```
Original Array: [1, 2, 3, 4, 5]
Index to be removed: 2
Resultant Array: [1, 2, 4, 5]
```

### 2.使用 Java 8 流

**进场:**

*   获取数组和索引。
*   使用 IntStream.range()方法将数组转换为 IntStream。
*   使用 filter()方法移除指定的索引元素。
*   使用 Map()和 toArray()方法映射并形成过滤元素的新数组。
*   返回形成的数组。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove an element
// from a specific index from an array

import java.util.Arrays;
import java.util.stream.IntStream;

class GFG {

    // Function to remove the element
    public static int[] removeTheElement(int[] arr, int index)
    {

        // If the array is empty
        // or the index is not in array range
        // return the original array
        if (arr == null
            || index < 0
            || index >= arr.length) {

            return arr;
        }

        // return the resultant array
        return IntStream.range(0, arr.length)
            .filter(i -> i != index)
            .map(i -> arr[i])
            .toArray();
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Get the array
        int[] arr = { 1, 2, 3, 4, 5 };

        // Print the resultant array
        System.out.println("Original Array: "
                        + Arrays.toString(arr));

        // Get the specific index
        int index = 2;

        // Print the index
        System.out.println("Index to be removed: "
                        + index);

        // Remove the element
        arr = removeTheElement(arr, index);

        // Print the resultant array
        System.out.println("Resultant Array: "
                        + Arrays.toString(arr));
    }
}
```

**Output**

```
Original Array: [1, 2, 3, 4, 5]
Index to be removed: 2
Resultant Array: [1, 2, 4, 5]
```

### 3.使用数组列表

**进场:**

*   获取数组和索引。
*   用数组元素组成一个数组列表。
*   使用 Remove()方法移除指定的索引元素。
*   使用 mapToInt()和 toArray()方法形成数组列表的新数组。
*   返回形成的数组。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove an element
// from a specific index from an array

import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.IntStream;

class GFG {

    // Function to remove the element
    public static int[] removeTheElement(int[] arr, int index)
    {

        // If the array is empty
        // or the index is not in array range
        // return the original array
        if (arr == null
            || index < 0
            || index >= arr.length) {

            return arr;
        }

        // Create ArrayList from the array
        List<Integer> arrayList = IntStream.of(arr)
                                    .boxed()
                                    .collect(Collectors.toList());

        // Remove the specified element
        arrayList.remove(index);

        // return the resultant array
        return arrayList.stream()
            .mapToInt(Integer::intValue)
            .toArray();
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Get the array
        int[] arr = { 1, 2, 3, 4, 5 };

        // Print the resultant array
        System.out.println("Original Array: "
                        + Arrays.toString(arr));

        // Get the specific index
        int index = 2;

        // Print the index
        System.out.println("Index to be removed: "
                        + index);

        // Remove the element
        arr = removeTheElement(arr, index);

        // Print the resultant array
        System.out.println("Resultant Array: "
                        + Arrays.toString(arr));
    }
}
```

**Output**

```
Original Array: [1, 2, 3, 4, 5]
Index to be removed: 2
Resultant Array: [1, 2, 4, 5]
```

### 4.使用 System.arraycopy()方法

**进场:**

*   获取数组和索引。
*   创建一个大小比原始数组小一倍的新数组。
*   使用 System.arraycopy()将从起始到索引的元素从原始数组复制到另一个数组。
*   使用 System.arraycopy()将元素从索引+ 1 一直复制到原始数组的末尾。
*   返回形成的数组。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove an element
// from a specific index from an array

import java.util.Arrays;

class GFG {

    // Function to remove the element
    public static int[] removeTheElement(int[] arr, int index)
    {

        // If the array is empty
        // or the index is not in array range
        // return the original array
        if (arr == null
            || index < 0
            || index >= arr.length) {

            return arr;
        }

        // Create another array of size one less
        int[] anotherArray = new int[arr.length - 1];

        // Copy the elements from starting till index
        // from original array to the other array
        System.arraycopy(arr, 0, anotherArray, 0, index);

        // Copy the elements from index + 1 till end
        // from original array to the other array
        System.arraycopy(arr, index + 1,
                        anotherArray, index,
                        arr.length - index - 1);

        // return the resultant array
        return anotherArray;
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Get the array
        int[] arr = { 1, 2, 3, 4, 5 };

        // Print the resultant array
        System.out.println("Original Array: "
                        + Arrays.toString(arr));

        // Get the specific index
        int index = 2;

        // Print the index
        System.out.println("Index to be removed: "
                        + index);

        // Remove the element
        arr = removeTheElement(arr, index);

        // Print the resultant array
        System.out.println("Resultant Array: "
                        + Arrays.toString(arr));
    }
}
```

**Output**

```
Original Array: [1, 2, 3, 4, 5]
Index to be removed: 2
Resultant Array: [1, 2, 4, 5]
```
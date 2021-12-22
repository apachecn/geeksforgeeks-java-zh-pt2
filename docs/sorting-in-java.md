# Java 中的排序

> 原文:[https://www.geeksforgeeks.org/sorting-in-java/](https://www.geeksforgeeks.org/sorting-in-java/)

每当我们听到排序算法开始发挥作用时，比如选择排序、冒泡排序、插入排序、基数排序、桶排序等等，但是如果我们仔细看这里，我们不会被要求使用任何类型的算法。借助 java 中存在的线性和非线性数据结构，它就像排序一样简单。因此，在 java 中，排序是在循环的帮助下借助蛮力完成的，在 Java 中，有两种内置的排序方法。

**Java 中的排序方式**

1.  Use cycle
2.  Use the sort () method of the Arrays class
3.  Use the sort method of the Collections class
4.  Sort on subarrays

让我们讨论这四个问题，并为每个问题提出一个代码。

**方式一:**使用回环

T5】JavaT7

```
// Java Program to sort an elements
// by bringing Arrays into play

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input array
        int arr[] = { 4, 3, 2, 1 };

        // Outer loop
        for (int i = 0; i < arr.length; i++) {

            // Inner nested loop pointing 1 index ahead
            for (int j = i + 1; j < arr.length; j++) {

                // Checking elements
                int temp = 0;
                if (arr[j] < arr[i]) {

                    // Swapping
                    temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }
            }

            // Printing sorted array elements
            System.out.print(arr[i] + " ");
        }
    }
}
```

T8T10**输出**T1

**方式二:**使用数组类**的排序()方法**

[数组。Sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 适用于原始数据类型的数组，默认情况下，这些数组也按升序排序。

**例 1**

## JAVA

```
// Java program to demonstrate working of
// sort() method of Arrays class

// Importing Arrays class from java.util package
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input array
        int[] arr = { 13, 7, 6, 45, 21, 9, 101, 102 };

        // Calling the sort() method present
        // inside Arrays class
        Arrays.sort(arr);

        // Printing and display sorted array
        System.out.printf("Modified arr[] : %s",
                          Arrays.toString(arr));
    }
}
```

**输出**

```
Modified arr[] : [6, 7, 9, 13, 21, 45, 101, 102]
```

**示例 2**

## JAVA

```
// A sample Java program to sort an array
// in descending order using Arrays.sort().
import java.util.Arrays;
import java.util.Collections;

public class GFG {
    public static void main(String[] args)
    {
        // Note that we have Integer here instead of
        // int[] as Collections.reverseOrder doesn't
        // work for primitive types.
        Integer[] arr = { 13, 7, 6, 45, 21, 9, 2, 100 };

        // Sorts arr[] in descending order
        Arrays.sort(arr, Collections.reverseOrder());

        System.out.printf("Modified arr[] : %s",
                          Arrays.toString(arr));
    }
}
```

**输出**

```
Modified arr[] : [100, 45, 21, 13, 9, 7, 6, 2]
```
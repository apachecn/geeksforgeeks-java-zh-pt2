# 根据 Java 中任意给定列的值对 2D 数组进行排序

> 原文:[https://www . geeksforgeeks . org/sorting-2d-array-根据值-给定-column-java/](https://www.geeksforgeeks.org/sorting-2d-array-according-values-given-column-java/)

给我们一个 N×M 阶的 2D 阵列和一个列号 K ( 1<=K<=m)。我们的任务是根据 k 列中的值对 2D 数组进行排序

示例:

```java
Input : If our 2D array is given as (Order 4X4) 
        39 27 11 42 
        10 93 91 90 
        54 78 56 89 
        24 64 20 65
        Sorting it by values in column 3 
Output : 39 27 11 42 
         24 64 20 65 
         54 78 56 89 
         10 93 91 90 

```

**想法是在 Java 中使用**[**array . sort**](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)。

```java
// Java Code to sort 2D Matrix
// according to any Column
import java.util.*;
class sort2DMatrixbycolumn {

    // Function to sort by column
    public static void sortbyColumn(int arr[][], int col)
    {
        // Using built-in sort function Arrays.sort
        Arrays.sort(arr, new Comparator<int[]>() {

          @Override              
          // Compare values according to columns
          public int compare(final int[] entry1, 
                             final int[] entry2) {

            // To sort in descending order revert 
            // the '>' Operator
            if (entry1[col] > entry2[col])
                return 1;
            else
                return -1;
          }
        });  // End of function call sort().
    }

    // Driver Code
    public static void main(String args[])
    {
        int matrix[][] = { { 39, 27, 11, 42 },
                           { 10, 93, 91, 90 },
                           { 54, 78, 56, 89 },
                           { 24, 64, 20, 65 } };
        // Sort this matrix by 3rd Column
        int col = 3;
        sortbyColumn(matrix, col - 1);

        // Display the sorted Matrix
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++)
                System.out.print(matrix[i][j] + " ");
            System.out.println();
        }
    }
}
```

输出:

```java
 39 27 11 42 
24 64 20 65 
54 78 56 89 
10 93 91 90 

```

**时间复杂度** : O(n Log n)，其中 n 为行数。这里的假设是 sort()函数使用 O(n Log n)排序算法。

本文由 **[丹麦 KALEEM](http://www.linkedin.com/in/mohdanishh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
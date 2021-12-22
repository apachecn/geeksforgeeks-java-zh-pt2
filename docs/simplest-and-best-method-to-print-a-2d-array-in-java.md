# 用 Java 打印 2D 数组最简单也是最好的方法

> 原文:[https://www . geesforgeks . org/最简单也是最好的方法来打印 java 中的 2d 数组/](https://www.geeksforgeeks.org/simplest-and-best-method-to-print-a-2d-array-in-java/)

给定一个 Java 中的 [2d 数组](https://www.geeksforgeeks.org/multidimensional-arrays-in-java/) arr，任务是打印这个 2d 数组的内容。

**方法 1: Loop 方法**
首先想到的是为 Loop 写一个嵌套，通过 arr[i][j]打印每个元素。

```java
// Java program to print 2d array
// using Loop method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Get the array
        int arr[][]
            = { { 1, 2, 3 },
                { 4, 5, 6 },
                { 7, 8, 9 } };

        // Print the array with the help of loop
        for (int i = 0; i < arr.length; i++) {

            System.out.print("[");
            for (int j = 0; j < arr[0].length; j++) {
                System.out.print(" " + arr[i][j] + ", ");
            }
            System.out.print("], ");
        }
    }
}
```

**Output:**

```java
[ 1,  2,  3, ], [ 4,  5,  6, ], [ 7,  8,  9, ],

```

**方法 2: [Arrays.deepToString()](https://www.geeksforgeeks.org/arrays-deeptostring-in-java-with-example/) 方法(最简单的方法)**
为此，我们将在 Java 的 util 包中使用 Arrays 类的 [deepToString()方法。这个方法帮助我们获取数组的字符串表示形式。借助 print()或 println()方法可以轻松打印该字符串。这是用 Java 打印 2D 数组的最好也是最简单的方法](https://www.geeksforgeeks.org/arrays-deeptostring-in-java-with-example/)

```java
// Java program to print 2d array
// using Arrays.deepToString() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Get the array
        int arr[][]
            = { { 1, 2, 3 },
                { 4, 5, 6 },
                { 7, 8, 9 } };

        // Print the array
        System.out.println(
            "Array: "
            + Arrays.deepToString(arr));
    }
}
```

**Output:**

```java
Array: [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

```
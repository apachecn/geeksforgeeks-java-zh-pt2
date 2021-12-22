# 在 Java 中反转一个数组

> 原文:[https://www.geeksforgeeks.org/reverse-an-array-in-java/](https://www.geeksforgeeks.org/reverse-an-array-in-java/)

给定一个数组，任务是在 Java 中反转给定的数组。

**示例:**

```java
Input : 1, 2, 3, 4, 5
Output :5, 4, 3, 2, 1

Input :  10, 20, 30, 40
Output : 40, 30, 20, 10
```

一个 [**数组**](https://www.geeksforgeeks.org/arrays-in-java/) 就是一个包含**一组元素** **的数据结构。**通常这些元素都是相同的数据类型，例如整数或字符串。数组通常在计算机程序中用于组织数据，以便可以快速对一组相关的值进行排序或搜索。阵列的所有项目都存储在连续的存储位置。

### 方法

在 Java 中有许多方法可以反转数组。这些是:

*   使用临时数组
*   使用交换
*   使用 Collections.reverse()方法
*   使用 StringBuilder.append()方法

### 1.使用临时数组

**第一种方法**如下:

*   输入数组的大小和数组的元素。
*   考虑一个取参数的反函数——数组(比如 arr)和数组的大小(比如 n)。
*   在函数内部，一个新的数组(第一个数组的数组大小为 arr)被初始化。数组 arr[]从第一个元素开始迭代，数组 arr[]的每个元素从后面放入新数组，即新数组从最后一个元素开始迭代。
*   这样，数组 arr[]的所有元素都反向放置在新数组中。
*   此外，我们可以从头开始遍历新数组，并打印数组的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Basic Java program that reverses an array

public class reverseArray {

    // function that reverses array and stores it 
    // in another array
    static void reverse(int a[], int n)
    {
        int[] b = new int[n];
        int j = n;
        for (int i = 0; i < n; i++) {
            b[j - 1] = a[i];
            j = j - 1;
        }

        // printing the reversed array
        System.out.println("Reversed array is: \n");
        for (int k = 0; k < n; k++) {
            System.out.println(b[k]);
        }
    }

    public static void main(String[] args)
    {
        int [] arr = {10, 20, 30, 40, 50};
        reverse(arr, arr.length);
    }
}
```

**Output**

```java
Reversed array is: 

50
40
30
20
10
```

### 2.使用交换

第二种方法**使用类似的代码输入和打印数组。但是，我们不会像上面的方法那样创建一个新数组。相反，我们反转原始数组本身。在这个方法中，我们交换数组的元素。第一个元素与最后一个元素交换。第二个元素与最后一个元素交换，以此类推。
例如，考虑数组[1，2，3，…。，n-2，n-1，n]。我们用 n 交换 1，用 n-1 交换 2，用 n-2 交换 3，然后。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program that reverses array
// in less number of swaps

public class arrayReverse {

    // function swaps the array's first element with last
    // element, second element with last second element and
    // so on
    static void reverse(int a[], int n)
    {
        int i, k, t;
        for (i = 0; i < n / 2; i++) {
            t = a[i];
            a[i] = a[n - i - 1];
            a[n - i - 1] = t;
        }

        // printing the reversed array
        System.out.println("Reversed array is: \n");
        for (k = 0; k < n; k++) {
            System.out.println(a[k]);
        }
    }

    public static void main(String[] args)
    {
        int[] arr = { 10, 20, 30, 40, 50 };
        reverse(arr, arr.length);
    }
}
```

****Output**

```java
Reversed array is: 

50
40
30
20
10
```** 

### **3.使用 [Collections.reverse()](https://www.geeksforgeeks.org/collections-reverse-java-examples/) 方法**

****第三种方法**是使用函数**Java . util . collections . reverse(List List)**方法。此方法反转指定列表中的元素。因此，我们首先使用**Java . util . arrays . aslist(array)**将数组转换为列表，然后反转列表。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Reversing an array using Java collections
import java.util.*;

public class reversingArray {

    // function reverses the elements of the array
    static void reverse(Integer a[])
    {
        Collections.reverse(Arrays.asList(a));
        System.out.println(Arrays.asList(a));
    }

    public static void main(String[] args)
    {
        Integer [] arr = {10, 20, 30, 40, 50};
        reverse(arr);
    }
}
```

****Output**

```java
[50, 40, 30, 20, 10]
```** 

### **4.使用 StringBuilder.append()方法**

**作为第四种方法**，如果你正在处理一个字符串数组，我们可以使用一个 StringBuilder，并在每个数组元素上附加一个 for 循环，从数组的长度开始递减，将 StringBuilder 转换为字符串，并拆分回一个数组。****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java Program for Reversing an array using StringBuilder

import java.util.Arrays;

class GFG {
    public static void main (String[] args) {
      String[] arr = {"Hello", "World"};
      StringBuilder reversed = new StringBuilder();

      for (int i = arr.length; i > 0; i--) {
          reversed.append(arr[i - 1]).append(" ");
      };

      String[] reversedArray = reversed.toString().split(" ");

      System.out.println(Arrays.toString(reversedArray));
    }
}**
```

******Output**

```java
[World, Hello]
```****
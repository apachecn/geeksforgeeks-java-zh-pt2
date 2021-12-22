# Java 中奇数和偶数索引处的偶数和奇数可被大小整除的数组之和

> 原文:[https://www . geeksforgeeks . org/数组之和-可被大小整除-在 java 中奇数和偶数索引处有偶数和奇数/](https://www.geeksforgeeks.org/sum-of-array-divisible-by-size-with-even-and-odd-numbers-at-odd-and-even-index-in-java/)

给定大小为 **N、**的数组 **arr[]** ，将给定数组转换为数组中的偶数出现在奇数索引处，数组中的奇数出现在偶数索引处，以及数组中的数字之和是否可被数组的大小整除。如果数组遵循所有属性，则数组有效，否则无效。

**如果一个数组符合所有给定的三个条件，则该数组有效:**

1.  在给定的数组 arr[]中，在每个偶数索引位置，它必须包含一个奇数。
2.  在给定的数组 arr[]中，在每个奇数索引位置，它必须包含一个偶数。
3.  给定数组 arr[]的和必须能被给定数组的大小整除。

**注:**数组基于 0 个索引。

**示例:**

```java
Input : arr = {1, 2, 3, 4, 5, 6, 9, 10} 
Output: "VALID"
Explanation: 
 1.Sum of given array is 40, and size of array is 8
 2.At every even index position array containing odd number
 3.At every odd position index array containing even number

Input : arr = {11, 4, 9, 3, 13}
Output: "INVALID"
Explanation: 
 1.Sum of given array is 40, and size of array is 4
 2.At index 3 it containing an odd value which does not follow given condition
Hence it is invalid.
```

**进场:**

*   遍历给定的数组，检查每个元素是否满足条件。
*   检查每个索引:
    *   如果指数是奇数，那么该指数的值必须是偶数。
    *   否则，如果指数是偶数，那么该指数的值一定是奇数。
    *   否则打印数组无效并返回。
*   存储每个给定元素的总和。
*   最后检查它是否能被给定的数组大小整除。
*   如果总和可被整除，则打印“有效”，否则打印“无效”。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Sum of Array Divisible by Size with Even
// and Odd Numbers at Odd and Even Index 
// in Java
public class Main {

    // check whether array is valid or not
    public static String validate(int[] arr)
    {
        // Finding size of given array
        int N = arr.length;

        // Store sum of given array
        int s = 0;

        // traverse the given array
        for (int i = 0; i < N; i++) {
            // store sum of elements
            s += arr[i];

            // if index is even and value is
            // odd, then continue
            if (i % 2 == 0 && arr[i] % 2 == 1)
                continue;

            // if index is odd and value is
            // even, then continue
            else if (i % 2 == 1 && arr[i] % 2 == 0)
                continue;

            // violeting given condition
            else
                return "INVALID";
        }

        // check last condition, sum is
        // divisible by size or not

        return s % N == 0 ? "VALID" : "INVALID";
    }
    // Driver Code
    public static void main(String[] args)
    {

        int[] arr = { 1, 2, 3, 4, 5, 6, 9, 10 };
        System.out.println(validate(arr));

        int[] barr = { 11, 4, 9, 3, 13 };
        System.out.println(validate(barr));
    }
}
```

**Output**

```java
VALID
INVALID
```

*   **时间复杂度:** O(N)
*   **空间复杂度:** O(1)
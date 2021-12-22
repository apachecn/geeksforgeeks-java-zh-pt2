# 替换 Java 向量的所有元素

> 原文:[https://www . geesforgeks . org/replacing-all-elements-of-Java-vector/](https://www.geeksforgeeks.org/replacing-all-elements-of-java-vector/)

一个向量的所有元素可以被一个特定的元素用 java 代替。乌提尔。**收藏。fill()方法。****fill()**方法的**Java . util . collections**类用于用指定的元素替换指定列表的所有元素。

*   让我们考虑以下向量:

![](img/8edae36d7c9cfe8d81860fc7facaa9fa.png)

替换前的向量

*   假设我们必须用**值 1** 替换所有元素，然后用 1 替换给定向量中的每个值之后，向量应该变成如下图所示:-

![](img/fdf0d3faf3810bbf28bae0f8a3801d6c.png)

替换后的向量

**算法:**

*   一种简单的方法是遍历整个向量并用给定值替换每个元素。然而，在 Java 中，我们有一个内置的方法 **Collections.fill()** 方法作为 Java Collections 的一部分，它取代了所有的元素。

该方法在线性时间内运行。

**语法:**

```
public static  void fill(List list, T obj)
```

**参数:**该方法以下列参数为参数

*   **列表–**要用指定元素填充的列表。
*   **obj–**填充指定列表的元素。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Replacing All 
// Elements of Java Vector

import java.io.*;
import java.util.Vector;
import java.util.Collections;
class GFG {
    public static void main (String[] args)
    {
      // Create a vector
      Vector<Integer> storage =new Vector<Integer>(6);

      // adding elements to the vector
      storage.add(20);      
      storage.add(10);
      storage.add(30);
      storage.add(40);
      storage.add(60);
      storage.add(70);

      // val to replace with 
      int val=1;

      // printing the vector before replacing 
      System.out.println("Vector before Replacing is: " + storage);

      // using Collections.fill to replace all the elements
      Collections.fill(storage,val);

      //printing the vector after replacing 
      System.out.println("Vector after Replacing is:  " + storage);

    }
}
```

**Output**

```
Vector before Replacing is: [20, 10, 30, 40, 60, 70]
Vector after Replacing is:  [1, 1, 1, 1, 1, 1]
```
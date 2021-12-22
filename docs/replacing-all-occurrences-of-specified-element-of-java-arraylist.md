# 替换 Java 数组列表中指定元素的所有出现

> 原文:[https://www . geeksforgeeks . org/replacing-all-exceptions-of-Java-ArrayList/](https://www.geeksforgeeks.org/replacing-all-occurrences-of-specified-element-of-java-arraylist/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中，是[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)接口的实现类。它允许重复的元素，并且保持元素的插入顺序。它会动态调整其容量。虽然它可能比标准数组慢，但在需要大量数组操作的程序中会有帮助。

**示例:**在本程序中，我们将首先创建一个整数数组列表，并使用 add()方法添加元素，现在我们将使用[对每个循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)迭代数组列表元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.ArrayList;
import java.util.Collections;
class GFG {
    public static void main(String[] args)
    {
        // ArrayList of Integers
        ArrayList<Integer> gfg = new ArrayList<>();

        // adding members into the list now
        gfg.add(1);
        gfg.add(20);
        gfg.add(21);
        gfg.add(13);
        gfg.add(21);
        gfg.add(10);
        gfg.add(21);

        // printing all the elements using for each loop
        for (Integer value : gfg) {
            System.out.println(value);
        }
    }
}
```

**Output**

```
1
20
21
13
21
10
21
```

**方法(使用 replaceAll()方法)**

在这个程序中，我们将创建一个整数数组列表，并使用 add()方法在其中添加元素，然后我们将使用 [replaceAll()](https://www.geeksforgeeks.org/collections-replaceall-method-in-java-with-examples/) 方法用 200 替换所有出现的 21。

**语法:**

```
public static  boolean replaceAll(List list, T oldVal, T newVal)
```

**参数:**该方法将以下参数作为参数

*   **列表:**要进行替换的列表。
*   **旧值:**要替换的旧值。
*   **新值:**新值，用来替换**旧值**。

**返回值:**如果列表包含一个或多个元素 e，则该方法返回**true**(oldVal = = null？e==null : oldVal.equals(e))。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Replacing All Occurrences of Specified
// Element of ArrayList

import java.io.*;
import java.util.ArrayList;
import java.util.Collections;

class GFG {
    public static void main(String[] args)
    {
        // ArrayList of Integers
        ArrayList<Integer> gfg = new ArrayList<>();

        // adding members into the list now
        gfg.add(1);
        gfg.add(20);
        gfg.add(21);
        gfg.add(13);
        gfg.add(21);
        gfg.add(10);
        gfg.add(21);

        // replacing 21 with 100 using replaceAll() method
        Collections.replaceAll(gfg, 21, 200);

        // printing all the elements using for each loop
        for (Integer value : gfg) {
            System.out.println(value);
        }
    }
}
```

**Output**

```
1
20
200
13
200
10
200
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// replaceAll() method for Integer value

import java.util.*;

public class GFG {
    public static void main(String[] argv) throws Exception
    {
        // creating object of List<String>
        List<String> list = new ArrayList<String>();

        // populate the vector
        list.add("?");
        list.add("For");
        list.add("?");

        // printing the vector
        System.out.println("Initial values are :" + list);

        // replacing value
        // using replaceAll() method
        Collections.replaceAll(list, "?", "Geeks");

        System.out.println("Value after replace :" + list);
    }
}
```

**Output**

```
Initial values are :[?, For, ?]
Value after replace :[Geeks, For, Geeks]
```
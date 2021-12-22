# 在 Java 中将列表分成两半

> 原文:[https://www . geesforgeks . org/split-a-list-in-Java-两半/](https://www.geeksforgeeks.org/split-a-list-into-two-halves-in-java/)

在这里，我们得到了一个列表，任务是将它分成两个新闻列表，如下图所示:

**插图:**

```
Input  : list = {1, 2, 3, 4, 5, 6}
Output : first = {1, 2, 3}, second = {4, 5, 6}

Input  : list = {1, 2, 3, 4, 5}
Output : first = {1, 2}, second = {3, 4, 5}
```

**方法:**

1.  Use cycle (naive method)
2.  The List class using the subList () method
3.  使用分区依据()方法的收集者类
4.  Use Google guava library

让我们讨论一下上面定义的方法的细节，并通过干净的 java 程序实现如下:

**方法 1:** 使用循环

**方法:**

1.  Create two new empty lists and assign the first half elements of the original list.
2.  Reset to enter the second empty list.

**示例:**

## Java

```
// Java Program to Split a List into Two Sublist

// Importing required classes
import java.util.ArrayList;
import java.util.List;

// Main class
public class GFG {

    // Method 1
    // To split a list into two sublists in Java
    public static List[] split(List<String> list)
    {

        // Creating two empty lists
        List<String> first = new ArrayList<String>();
        List<String> second = new ArrayList<String>();

        // Getting size of the list
        // using size() method
        int size = list.size();

        // Step 1
        // (First size)/2 element copy into list
        // first and rest second list
        for (int i = 0; i < size / 2; i++)
            first.add(list.get(i));

        // Step 2
        // (Second size)/2 element copy into list first and
        // rest second list
        for (int i = size / 2; i < size; i++)
            second.add(list.get(i));

        // Returning a List of array
        return new List[] { first, second };
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an ArrayList of string type
        List<String> list = new ArrayList<String>();

        // Adding elements to list object
        // using add() method
        list.add("Geeks");
        list.add("Practice");
        list.add("Contribute");
        list.add("IDE");
        list.add("Courses");

        // Calling split method which return List of array
        List[] lists = split(list);

        // Printing specific elements of list by
        // passing arguments with in
        System.out.println(lists[0]);
        System.out.println(lists[1]);
    }
}
```

**输出**

```
[Geeks, Practice]
[Contribute, IDE, Courses]
```

**方法 2:** 使用 List 类的 subList()方法

它返回此列表中指定索引(包括)到另一个索引(排除)之间的部分的视图。例如，让我们从 2 到 5 任意取值，这里索引 2 将只包括。如果两个指定的索引相等，则返回的列表为空。List.subList()返回了一个列表，因此返回列表中的非结构性更改。

**例:**

## 爪哇

```
// Java Program to Split a List into Two SubList
// Using subList() method of List clas

// Importing required classes
import java.util.ArrayList;
import java.util.List;

// Main class
public class GFG {

    // Method 1
    // To split a list into two sublists in Java
    public static List[] split(List<String> list)
    {

        // Finding the size of the list using List.size()
        // and putting in a variable
        int size = list.size();

        // Creating new list and inserting values which is
        // returned by List.subList() method
        List<String> first
            = new ArrayList<>(list.subList(0, (size) / 2));
        List<String> second = new ArrayList<>(
            list.subList((size) / 2, size));

        // Returning an List of array
        return new List[] { first, second };
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creatingan ArrayList of String type
        List<String> list = new ArrayList<String>();

        // Adding elements to List object
        // Custom input elements
        list.add("Geeks");
        list.add("Practice");
        list.add("Contribute");
        list.add("IDE");
        list.add("Courses");

        // Calling split method which return List of array
        List[] lists = split(list);

        // Printing specific elements of list by
        // passing arguments with in
        System.out.println(lists[0]);
        System.out.println(lists[1]);
    }
}
```

**输出**

```
[Geeks, Practice]
[Contribute, IDE, Courses]
```
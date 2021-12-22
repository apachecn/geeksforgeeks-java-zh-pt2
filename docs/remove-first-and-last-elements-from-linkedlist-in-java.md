# 从 Java 中的链接列表中删除第一个和最后一个元素

> 原文:[https://www . geesforgeks . org/remove-first-and-last-elements-from-linked list-in-Java/](https://www.geeksforgeeks.org/remove-first-and-last-elements-from-linkedlist-in-java/)

[**Java . util . LinkedList . remove First()**](https://www.geeksforgeeks.org/linkedlist-removefirst-method-in-java/)方法用于从 LinkedList 中移除第一个元素。

使用 [**方法从链表中删除最后一个元素。这两种方法都在移除元素后返回元素。**](https://www.geeksforgeeks.org/linkedlist-removelast-method-in-java/)

#### 1. removeFirst（）

**语法:**

```
LinkedList.remove()
```

**参数:**该功能不取任何参数。

**返回值**:该方法返回列表的第一个元素或位于列表头部的元素。

#### 2\. removeLast()

**语法:**

```
LinkedList.removeLast()
```

**参数:**该功能不取任何参数。

**返回值:**该方法返回最后一个元素或列表尾部的元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the Java.util.LinkedList.remove() method
// and Java.util.LinkedList.removeLast() method

import java.util.LinkedList;

class GFG {
    public static void main (String[] args) {

        // Creating an LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geek");
        list.add("for");
        list.add("Geeks");
        list.add("2020");
        list.add("2021");

        // Displaying the list
        System.out.println("LinkedList:\t" + list);

        // Remove the tail using removeLast()
        System.out.println("The last element is removed:\t" + list.removeLast());

        // Displaying the final list
        System.out.println("Final LinkedList:\t" + list);

        // Remove the head using remove()
        System.out.println("The first element is removed:\t" + list.removeFirst());

        // Displaying the final list
        System.out.println("Final LinkedList:\t" + list);
    }
}
```

**Output**

```
LinkedList:    [Geek, for, Geeks, 2020, 2021]
The last element is removed:    2021
Final LinkedList:    [Geek, for, Geeks, 2020]
The first element is removed:    Geek
Final LinkedList:    [for, Geeks, 2020]

```
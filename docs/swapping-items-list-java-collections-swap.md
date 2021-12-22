# 用示例

交换列表中的项目

> 原文:[https://www . geesforgeks . org/swapping-items-list-Java-collections-swap/](https://www.geeksforgeeks.org/swapping-items-list-java-collections-swap/)

**java.util.Collections . swap()**方法是一个 Java . util . collections 类方法。它交换给定列表中指定位置的元素。

```java
// Swaps elements at positions "i" and "j" in myList.
public static void swap(List mylist, int i, int j)

It throws IndexOutOfBoundsException if either i
or j is out of range.

```

```java
// Java program to demonstrate working of Collections.swap
import java.util.*;

public class GFG
{
    public static void main(String[] args)
    {
        // Let us create a list with 4 items
        ArrayList<String>  mylist =
                        new ArrayList<String>();
        mylist.add("code");
        mylist.add("practice");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");

        System.out.println("Original List : \n" + mylist);

        // Swap items at indexes 1 and 2
        Collections.swap(mylist, 1, 2);

        System.out.println("\nAfter swap(mylist, 1, 2) : \n"
                           + mylist);

        // Swap items at indexes 1 and 3
        Collections.swap(mylist, 3, 1);

        System.out.println("\nAfter swap(mylist, 3, 1) : \n"
                           + mylist);
    }
}
```

输出:

```java
Original List : Original List : 
[code, practice, quiz, geeksforgeeks]

After swap(mylist, 1, 2) : 
[code, quiz, practice, geeksforgeeks]

After swap(mylist, 3, 1) : 
[code, geeksforgeeks, practice, quiz]

```

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
。
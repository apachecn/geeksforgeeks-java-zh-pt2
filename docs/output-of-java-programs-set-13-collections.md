# Java 程序输出|第 13 集(集合)

> 原文:[https://www . geesforgeks . org/output-of-Java-programs-set-13-collections/](https://www.geeksforgeeks.org/output-of-java-programs-set-13-collections/)

先决条件–[Java 中的集合](https://www.geeksforgeeks.org/collections-in-java-2/)

**1)以下程序的输出是什么？**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

public class priorityQueue {
    public static void main(String[] args)
    {
        PriorityQueue<Integer> queue
            = new PriorityQueue<>();
        queue.add(11);
        queue.add(10);
        queue.add(22);
        queue.add(5);
        queue.add(12);
        queue.add(2);

        while (queue.isEmpty() == false)
            System.out.printf("%d ", queue.remove());

        System.out.println("\n");
    }
}
```

a)11 10 22 5 12 2
b)2 12 5 22 10 11
c)2 5 10 11 12 22
d)22 12 11 10 5 2

**年。(c)**

**<u>解释</u> :** 无论输入的顺序是什么，当调用 remove()方法时，优先级队列总是从队列中输出最小的元素。

**2)以下程序的输出是什么？**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

public class Treeset {
    public static void main(String[] args)
    {
        TreeSet<String> treeSet = new TreeSet<>();

        treeSet.add("Geeks");
        treeSet.add("For");
        treeSet.add("Geeks");
        treeSet.add("GeeksforGeeks");

        for (String temp : treeSet)
            System.out.printf(temp + " ");

        System.out.println("\n");
    }
}
```

a)极客对极客极客暴发户
b)极客对极客暴发户
c)极客极客暴发户
d)极客暴发户极客

**年。(c)**

**<u>解释</u> :** 一个树集合按照插入其中的升序对数据进行排序。因此，输出字符串包含以升序排列的所有字符串。TreeSet 不包含任何重复的元素，因为它是一个集合。所以在输出中，只有一个字符串“极客”。

**3)以下程序的输出是什么？**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

public class linkedList {
    public static void main(String[] args)
    {
        List<String> list1 = new LinkedList<>();
        list1.add("Geeks");
        list1.add("For");
        list1.add("Geeks");
        list1.add("GFG");
        list1.add("GeeksforGeeks");

        List<String> list2 = new LinkedList<>();
        list2.add("Geeks");

        list1.removeAll(list2);

        for (String temp : list1)
            System.out.printf(temp + " ");

        System.out.println();
    }
}
```

a)极客 GFG 极客乔治
b)极客 GFG 极客乔治
c)GFG 极客 T2 d)GFG 极客乔治

**年。(d)**

**<u>解释</u> :** list1.removeAll(list2)函数从 list1 中删除 list2 中出现的所有字符串。在这里，字符串“极客”出现在列表 2 中，所以列表 1 中所有包含“极客”数据的链表节点都从列表 1 中删除。

**4)给定的选项中，哪一个是可能的输出？**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

public class hashSet {
    public static void main(String[] args)
    {
        HashSet<String> hashSet = new HashSet<>();
        hashSet.add("Geeks");
        hashSet.add("For");
        hashSet.add("Geeks");
        hashSet.add("GeeksforGeeks");

        System.out.println(hashSet);
    }
}
```

a)【极客，为，极客，极客暴发户】
b)【极客暴发户，极客，为】

**年。(b)**

**<u>解释</u> :** 一个 HashSet 是一个集合，作为一个集合不包含任何重复的元素因此，字符串‘Geeks’在输出中只出现一次。

**5)以下程序的输出是什么？**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

public class stack {
    public static void main(String[] args)
    {
        List<String> list = new LinkedList<>();
        list.add("Geeks");
        list.add("For");
        list.add("Geeks");
        list.add("GeeksforGeeks");
        Iterator<Integer> iter = list.iterator();

        while (iter.hasNext())
            System.out.printf(iter.next() + " ");

        System.out.println();
    }
}
```

a)极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极客专用极

**年。(d)**

**<u>解释</u> :** 为迭代整数而制作的迭代器不能用于迭代字符串数据类型。修正程序:[https://ide.geeksforgeeks.org/DgeN0P](https://ide.geeksforgeeks.org/DgeN0P)

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 使用 Java 列表迭代器替换数组列表中的元素

> 原文:[https://www . geesforgeks . org/replace-an-element-from-ArrayList-use-Java-listiterator/](https://www.geeksforgeeks.org/replace-an-element-from-arraylist-using-java-listiterator/)

要替换数组列表中的元素，可以使用列表迭代器接口的 **set()** 方法。ListIterator 的 **set()** 方法将替换由 **next()或 previous()** 方法返回的最后一个元素以及给定的元素。

**使用如下所示的列表迭代器替换元素的两种方式是:**

1.  替换第一个元素
2.  替换最后一个元素

**替换第一个元素:**

**接近**

*   创建数组列表

```
ArrayList<Integer> list = new ArrayList<Integer>();

list.add(9);
list.add(11);
list.add(12);
list.add(13);
list.add(14);
list.add(15):
```

*   假设我们需要将列表的第一个元素 **9** 替换为 **10。**首先，我们将使用 ListIterator，用 next()方法返回 List 中的下一个元素。

```
ListIterator<Integer> iterator = list.listIterator();

iterator.next();
```

*   现在，使用 set()方法替换列表中的元素。这里我们将替换迭代器的第一个元素，它可以用任何指定的值替换(在我们的例子中，我们需要用 **10** 替换它)。

```
iterator.set(10);
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to replace an element
// from ArrayList using Java ListIterator

import java.util.ArrayList;
import java.util.ListIterator;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<Integer> list = new ArrayList<Integer>();
        list.add(9);
        list.add(11);
        list.add(12);
        list.add(13);
        list.add(14);
        list.add(15);

        System.out.println("Before Replacing...");

        // Printing the original list
        for (int i : list) {

            System.out.println(i);

        }

        ListIterator<Integer> iterator = list.listIterator();

        // Replacing the first element
        iterator.next();
        iterator.set(10);

        System.out.println("After replacing...");

        // Printing the list after replacement
        for (int i : list) {

            System.out.println(i);

        }
    }
}
```

**Output**

```
Before Replacing...
9
11
12
13
14
15
After replacing...
10
11
12
13
14
15
```

**替换最后一个元素:**

**接近**

*   使用上面相同的方法，数组列表中任何位置的任何元素都可以用任何值替换。
*   创建一个名称数组列表，并向其中添加一些名称–

```
ArrayList<String> name = new ArrayList<>();

name.add("Yash");
name.add("Akash");
name.add("Amar");
name.add("Abhishek");
name.add("Rajnikanth");
```

*   假设我们需要将“**拉吉尼坎塔**”替换为“**莫希特**”。
*   现在，使用列表迭代器，我们将迭代到列表的最后一个元素，然后替换它

```
ListIterator<String> iterator = name.listIterator();
while(iterator.hasNext())
{
    iterator.next();    
}

iterator.set("Mohit");
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to replace an element
// from ArrayList using Java ListIterator

import java.util.ArrayList;
import java.util.ListIterator;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<String> name = new ArrayList<>();
        name.add("Yash");
        name.add("Akash");
        name.add("Amar");
        name.add("Abhishek");
        name.add("Rajnikanth");

        ListIterator<String> iterator = name.listIterator();

        System.out.println("Before Replacing...");

        // Printing the original list
        while (iterator.hasNext()) {
            System.out.print(iterator.next()+" ");
        }

        // Simce the iterator was on last element
        // so the set function used here will replace
        // the last element
        iterator.set("Mohit");

        System.out.println();
        System.out.println("After Replacing...");

        for (String n : name) {
            System.out.print(n+" ");
        }
    }
}
```

**Output**

```
Before Replacing...
Yash Akash Amar Abhishek Rajnikanth 
After Replacing...
Yash Akash Amar Abhishek Mohit
```
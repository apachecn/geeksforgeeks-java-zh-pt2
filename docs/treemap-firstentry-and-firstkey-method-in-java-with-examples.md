# Java 中的 TreeMap firstEntry()和 firstKey()方法，示例

> 原文:[https://www . geesforgeks . org/tree map-first entry-和-first key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-firstentry-and-firstkey-method-in-java-with-examples/)

Java.util.TreeMap 中有两个 first()的**和**变体，本文将讨论这两个变体。

## **方法 1:** 第一个条目()

它返回与该映射中最小键相关联的键值映射，如果该映射为空，则返回 null。

**语法:**

```
public Map.Entry firstEntry()
```

**返回类型:**如果映射为空，则返回键最少且为空的条目。

**例:**

## 爪哇

```
// Java Program to Illustrate Working of firstKey() Method
// of TreeMap class

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeMap by
        // declaring object of integer, strings pairs
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // Populating values in the TreeMap
        // using put() method
        treemap.put(2, "two");
        treemap.put(7, "seven");
        treemap.put(3, "three");
        treemap.put(1, "one");
        treemap.put(6, "six");
        treemap.put(9, "nine");

        // Printing the lowest entry in TreeMap by
        // using firstEntry() method
        System.out.println("Lowest entry is: "
                           + treemap.firstEntry());
    }
}
```

**输出:**

```
Lowest entry is: 1=one
```

## **方法二:firstKey()**

它返回当前地图中的第一个(最低的)键。

**语法:**

```
public K firstKey()
```

**返回类型:**当前在此地图中的第一个(最低)键。

**异常抛出:**[NoSuchElementException](https://www.geeksforgeeks.org/how-to-fix-java-util-nosuchelementexception-in-java/)**T5】如果此地图为空则抛出。**

**例:**

## 爪哇

```
// Java Program to Demonstrate firstKey() Method
// of TreeMap class

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeMap by
        // declaring object of integer, strings pairs
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // Populating values in the TreeMap
        // using put() method
        treemap.put(2, "two");
        treemap.put(1, "one");
        treemap.put(3, "three");
        treemap.put(6, "six");
        treemap.put(5, "five");
        treemap.put(9, "nine");

        // Printing the lowest entry in TreeMap by
        // using firstKey() method
        System.out.println("Lowest key is: "
                           + treemap.firstKey());
    }
}
```

**输出:**

```
Lowest key is: 1
```

**实现:**这些功能可以用来获取给定列表中排名最好的人，也可以用来分配完成任务时间最少的人获胜的赢家。后一个问题将在下面讨论。

**例:**实际应用

T4】爪哇 T6

```
// Java Program to Demonstrate Application Usage
// of firstKey() and firstEntry() Methods
// of TreeMap class

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        // of Integer and String times of participants
        // In seconds
        TreeMap<Float, String> time
            = new TreeMap<Float, String>();

        // Populating the time taken to complete task
        // using put() method
        time.put(2.32f, "Astha");
        time.put(7.43f, "Manjeet");
        time.put(1.3f, "Shambhavi");
        time.put(5.63f, "Nikhil");
        time.put(6.26f, "Vaishnavi");

        // Printing person with least time
        // using of firstEntry() method
        System.out.println("Winner with lowest time is : "
                           + time.firstEntry());
    }
}
```

T7

**输出:**

```
Winner with lowest time is : 1.3=Shambhavi
```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# Java 中的树形图下降键集()方法，示例

> 原文:[https://www . geesforgeks . org/tree map-dependingkeyset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-descendingkeyset-method-in-java-with-examples/)

**树地图类**的**下降键集()**方法返回地图中包含的键的反向顺序*导航键集* *视图*。集合的迭代器以降序返回键。

**注意:**集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。

**语法:**

```
public NavigableSet<K> descendingKeySet()

```

**参数:** 该方法不取任何参数。

**返回值:**该方法返回地图中包含的值的可导航集合视图。

**异常:**该方法不抛出任何异常。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to show the working
// of descendingKeySet() Method
import java.io.*;
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // creating tree map of Integer and String
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // populating tree map using put()
        treemap.put(3, "three");
        treemap.put(1, "one");
        treemap.put(2, "two");
        treemap.put(0, "zero");
        treemap.put(7, "seven");
        treemap.put(6, "six");

        // putting values in navigable set
        // use of descendingKeySet
        NavigableSet set1 = treemap.descendingKeySet();

        System.out.println("Navigable set values are: "
                           + set1);
    }
}
```

**输出:**

```
Navigable set values are: [7, 6, 3, 2, 1, 0]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to show the working
// of descendingKeySet() Method
import java.io.*;
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // creating tree map of Integer and String
        TreeMap<Integer, String> geeks
            = new TreeMap<Integer, String>();

        // putting values in navigable set
        geeks.put(1, "Guru");
        geeks.put(2, "Ayush");
        geeks.put(3, "Devesh");
        geeks.put(4, "Kashish");

        System.out.println("TreeMap values :- " + geeks);

        // use of descendingKeySet
        NavigableSet nevigableSet
            = geeks.descendingKeySet();

        System.out.println("Reverse key values:- "
                           + nevigableSet);
    }
}
```

**输出:**

```
TreeMap values :- {1=Guru, 2=Ayush, 3=Devesh, 4=Kashish}
Reverse key values:- [4, 3, 2, 1]

```
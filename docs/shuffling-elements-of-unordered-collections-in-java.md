# 在 Java 中洗牌无序集合的元素

> 原文:[https://www . geeksforgeeks . org/shuffling-元素无序-java 中的集合/](https://www.geeksforgeeks.org/shuffling-elements-of-unordered-collections-in-java/)

java 中的无序集合不提供任何顺序，即元素不能使用特定的索引或排序来访问，就像我们在有序集合(如 [List](https://www.geeksforgeeks.org/list-interface-java-examples/) )的情况下所做的那样。**集**和**地图**是无序收集的例子。

在 java 中，我们不能直接使用**[**collections . shuffle()**](https://www.geeksforgeeks.org/collections-shuffle-java-examples/)**方法来打乱无序的集合，因为它需要一个**列表**作为参数。****

******用于混洗元素，******

*   ****我们必须首先将无序集合的元素存储在一个列表中，然后我们可以使用 **Collections.shuffle()** 方法对其进行洗牌。****

******1)混洗集合中的元素******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to demonstrate the shuffling
// of a set

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Creating a Hashset
        Set<Integer> st = new HashSet<>();

        // Inserting elements to the set
        st.add(91);
        st.add(0);
        st.add(55);
        st.add(10);
        st.add(9);

        // 9 won't be inserted to the Set as Hashset does
        // not take duplicate entries
        st.add(9);

        // Displaying the elements of the set
        System.out.print("The Set before shuffling: ");

        for (int i : st)
            System.out.print(i + " ");

        System.out.println();

        // Creating a List and storing the values of the
        // Set inside it by passing the Set as a parameter
        // to the constructor
        List<Integer> list = new ArrayList<>(st);

        // Shuffling the elements of the list using using
        // Collections.shuffle() method
        Collections.shuffle(list);

        // Displaying the elements of the list
        System.out.print("The List (containing elements of the Set) after shuffling: ");

        for (int i : list)
            System.out.print(i + " ");
    }
}**
```

******Output**

```
The Set before shuffling: 0 55 9 10 91 
The List (containing elements of the Set) after shuffling: 55 0 91 10 9 
```**** 

******2)洗牌地图的元素******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to demonstrate the shuffling 
// of a map

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Creating a HashMap
        Map<Integer, String> mp
            = new HashMap<Integer, String>();

        // Inserting some values inside the HashMap
        mp.put(1, "Geeks");
        mp.put(2, "for");
        mp.put(3, "Geeks");
        mp.put(4, "is");
        mp.put(5, "love");

        // Displaying the map
        System.out.println("The Map before shuffling: ");

        for (Map.Entry<Integer, String> entry :mp.entrySet())
            System.out.println(entry.getKey() + " "
                               + entry.getValue());

        System.out.println();

        // Creating a list and storing the elements of the
        // Map inside of it
        List<Map.Entry<Integer, String> > list
            = new ArrayList<>(mp.entrySet());

        // Shuffling the list using shuffle() method
        Collections.shuffle(list);

        // Displaying the list
        System.out.println("The List (containing the elements of the Map)" 
                           + " After shuffing: ");

        for (Map.Entry<Integer, String> entry : list)
            System.out.println(entry.getKey() + " "
                               + entry.getValue());
        System.out.println();
    }
}**
```

******Output**

```
The Map before shuffling: 
1 Geeks
2 for
3 Geeks
4 is
5 love

The List (containing the elements of the Map) After shuffing: 
2 for
5 love
4 is
3 Geeks
1 Geeks
```****
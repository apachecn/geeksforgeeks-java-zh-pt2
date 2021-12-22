# 使用 Java 中的可比接口按值对链接哈希表进行排序

> 原文:[https://www . geeksforgeeks . org/sort-link edhashmap-by-values-使用 java 中的可比接口/](https://www.geeksforgeeks.org/sort-linkedhashmap-by-values-using-comparable-interface-in-java/)

[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)就像哈希表一样，有一个额外的特性，即保持插入其中的元素的顺序。假设您已经在 java 中浏览过 LinkedHashMap，并且知道 LinkedHashMap。

**语法:**

```
int compare(T obj) ;
```

插图:

> ```
> Input  : { GEEKS=1, geeks=3, for=2 }
> Output : { GEEKS=1, for=2, geeks=3 }
> 
> Input  : { 101 = 2, 102 = 9, 103 = 1, 105 = 7 }
> Output : { 103 = 1, 101 = 2, 105 = 7, 102 = 9 }
> ```

**方法:**在使用 Comparable 接口按值对 LinkedHashMap 进行排序时，这个接口对实现它的每个类的对象强加了一个总的排序。这种排序称为类的自然排序，类的比较器方法称为其自然比较方法。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort the values of LinkedHashMap

// Importing required classes from
// java.util package
import java.util.*;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.Map.*;

// Class 
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an LinkedHashMap object
        LinkedHashMap<String, Integer> l_map
            = new LinkedHashMap<String, Integer>();

        // Adding element to LinkedHashSet
        // Custom inputs
        l_map.put("Computer", 1);
        l_map.put("Science", 3);
        l_map.put("Portal", 2);

        // Display message
        System.out.print(
            "LinkedHashMap without sorting : ");

        // Print the elements of Map in above object
        // just after addition without sorting
        System.out.println(l_map);

        // Convert key-value from the LinkedHashMap to List
        // using entryset() method
        List<Map.Entry<String, Integer> > list
            = new ArrayList<Map.Entry<String, Integer> >(
                l_map.entrySet());

        // Comparable Interface function to
        // sort the values of List
        Collections.sort(
            list,
            new Comparator<Map.Entry<String, Integer> >() {
                // Comparing entries
                public int compare(
                    Entry<String, Integer> entry1,
                    Entry<String, Integer> entry2)
                {
                    return entry1.getValue()
                        - entry2.getValue();
                }
            });

        // Clear the above LinkedHashMap
        // using clear() method
        l_map.clear();

        // Iterating over elements using for each loop
        for (Map.Entry<String, Integer> entry : list) {

            // Put all sorted value back to the
            // LinkedHashMap
            l_map.put(entry.getKey(), entry.getValue());
        }

        // Display and print
        // the sorted value of LinkedHashMap
        System.out.println(
            "LinkedHashMap after sorting   : " + l_map);
    }
}
```

**Output**

```
LinkedHashMap without sorting : {Computer=1, Science=3, Portal=2}
LinkedHashMap after sorting   : {Computer=1, Portal=2, Science=3}

```
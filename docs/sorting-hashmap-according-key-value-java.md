# 根据 Java 中的键对 HashMap 进行排序

> 原文:[https://www . geesforgeks . org/sorting-hashmap-accord-key-value-Java/](https://www.geeksforgeeks.org/sorting-hashmap-according-key-value-java/)

我们以 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 的形式给出了学生得分的详细情况，其中学生的名字为 Key，得分为 Value。我们的任务是根据关键值对地图进行排序，即按照字母顺序(词典顺序)排列学生的姓名。
**例:**

```
Input : Key = Jayant, Value = 80
        Key = Anushka, Value = 80
        Key = Amit, Value = 75
        Key = Abhishek, Value = 90
        Key = Danish, Value = 40
Output : Sorted Map according to Names:
         Key = Abhishek, Value = 90
         Key = Amit, Value = 75
         Key = Anushka, Value = 80
         Key = Danish, Value = 40
         Key = Jayant, Value = 80
```

**使用 TreeMap (putAll 方法)**

想法是把 HashMap 的所有数据放入[树形图](https://www.geeksforgeeks.org/hashmap-treemap-java/)中。树形图遵循基于[红黑树](https://www.geeksforgeeks.org/red-black-tree-set-1-introduction-2/)的实现。地图根据其关键字的自然顺序进行排序。[点击这里了解更多](https://docs.oracle.com/javase/7/docs/api/java/util/TreeMap.html)。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Code to sort Map by key value
import java.util.*;
class sortmapKey {

    // This map stores unsorted values
    static Map<String, Integer> map = new HashMap<>();

    // Function to sort map by Key
    public static void sortbykey()
    {
        // TreeMap to store values of HashMap
        TreeMap<String, Integer> sorted = new TreeMap<>();

        // Copy all data from hashMap into TreeMap
        sorted.putAll(map);

        // Display the TreeMap which is naturally sorted
        for (Map.Entry<String, Integer> entry : sorted.entrySet())
            System.out.println("Key = " + entry.getKey() +
                         ", Value = " + entry.getValue());       
    }

    // Driver Code
    public static void main(String args[])
    {
        // putting values in the Map
        map.put("Jayant", 80);
        map.put("Abhishek", 90);
        map.put("Anushka", 80);
        map.put("Amit", 75);
        map.put("Danish", 40);

        // Calling the function to sortbyKey
        sortbykey();
    }
}
```

**Output**

```
Key = Abhishek, Value = 90
Key = Amit, Value = 75
Key = Anushka, Value = 80
Key = Danish, Value = 40
Key = Jayant, Value = 80
```
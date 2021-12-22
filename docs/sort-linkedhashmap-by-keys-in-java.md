# 在 Java 中按键对链接的哈希表进行排序

> 原文:[https://www . geeksforgeeks . org/sort-link edhashmap-by-key-in-Java/](https://www.geeksforgeeks.org/sort-linkedhashmap-by-keys-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 保持插入顺序。将链接哈希表转换成树形图，然后打印出本质上是排序的树形图的键。

**示例:**

```java
Input: linkedHashMap = {{5,4}, {3,44}, {4,15}, {1,20}, {2,11}}
Output:
key -> 1 : value -> 20
key -> 2 : value -> 11
key -> 3 : value -> 44
key -> 4 : value -> 15 
key -> 5: value -> 4
```

**进场:**

1.  以 LinkedHashMap 为输入。
2.  创建新的树形图。
3.  将 LinkedHashMap 对象传递到 TreeMap 的构造函数中。
4.  打印树形图对象的关键点。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Sort LinkedHashMap by keys in Java
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        LinkedHashMap<Integer, Integer> lMap
            = new LinkedHashMap<>();

        // adding key-value pairs to LinkedHashMap object
        lMap.put(5, 4);
        lMap.put(3, 44);
        lMap.put(4, 15);
        lMap.put(1, 20);
        lMap.put(2, 11);
        System.out.println("After Sorting :\n");

        // convert to TreeMap
        Map<Integer, Integer> map = new TreeMap<>(lMap);

        // iterate acc to ascending order of keys
        for (Integer sKey : map.keySet()) {
            System.out.println("Key -> " + sKey
                               + ":  Value -> "
                               + lMap.get(sKey));
        }
    }
}
```

**Output**

```java
After Sorting :

Key -> 1:  Value -> 20
Key -> 2:  Value -> 11
Key -> 3:  Value -> 44
Key -> 4:  Value -> 15
Key -> 5:  Value -> 4
```
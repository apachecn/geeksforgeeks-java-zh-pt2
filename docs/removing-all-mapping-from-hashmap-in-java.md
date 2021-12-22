# 从 Java 的 HashMap 中移除所有映射

> 原文:[https://www . geesforgeks . org/remove-all-mapping-from-hashmap-in-Java/](https://www.geeksforgeeks.org/removing-all-mapping-from-hashmap-in-java/)

[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)用于当您想要将一个键与一个值相关联时，列表是一个有序的集合。Map 是 Java 集合框架中的一个接口，而 HashMap 是 Map 接口的一个实现。[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)可以有效地定位基于键的值以及插入和删除基于键的值。

为了从 java 的 HashMap 中移除所有映射，我们可以使用各种方法:

1.  clear()方法
2.  通过迭代器移除
3.  removeIf()方法

**法 1:使用** [**清()**](https://www.geeksforgeeks.org/hashmap-clear-method-in-java/) **法**

java 中的 java.util.HashMap.clear()方法用于清除和移除指定 HashMap 中的所有元素或映射。

**语法:**

```java
Hash_Map.clear()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to remove mappings from
// HashMap using clear() method

import java.io.*;

import java.util.*;
class GFG {
    public static void main(String[] args)
    {

        HashMap<String, Integer> gfg = new HashMap<>();

        // adding values in hashMap 1
        gfg.put("DSA", 100);
        gfg.put("Problem Solving", 100);
        gfg.put("Development", 99);
        gfg.put("Interviews", 99);
        gfg.put("Competitive Programming", 97);
        gfg.put("FANG", 99);

        // printing the size and elements
        System.out.println("-------before removing------");
        System.out.println(gfg);
        System.out.println(gfg.size());

        // clear() method
        gfg.clear();

        System.out.println("--------After removing-------");
        System.out.println(gfg);
        System.out.println(gfg.size());
    }
}
```

**Output**

```java
-------before removing------
{DSA=100, FANG=99, Competitive Programming=97, Problem Solving=100, Development=99, Interviews=99}
6
--------After removing-------
{}
0
```

**方法二:通过** [**迭代器**](https://www.geeksforgeeks.org/iterators-in-java/) 移除

*   在这种方法中，您将使用迭代器迭代地图，然后在迭代器上调用 remove。
*   在这种情况下，我们正在迭代从调用 keySet()方法获得的键。
*   hasNext()用于检查集合中是否存在下一个元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to remove each key value pair
// by iterating over the Hashmap

import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        HashMap<String, Integer> gfg = new HashMap<>();

        // adding values in hashMap 1
        gfg.put("DSA", 100);
        gfg.put("Problem Solving", 100);
        gfg.put("Development", 99);
        gfg.put("Interviews", 99);
        gfg.put("Competitive Programming", 97);
        gfg.put("FANG", 99);

        // printing the size and elements
        System.out.println("-------before removing------");
        System.out.println(gfg);
        System.out.println(gfg.size());

        // getting all keys of map using keySet()

        Set keyset = gfg.keySet();

        // iterating over the keys and removing
        // hasNext() method is used to check whether next
        // element present inside the collection or not

        Iterator itr = keyset.iterator();
        while (itr.hasNext()) {
            itr.next();
            itr.remove();
        }

        System.out.println("--------After removing-------");
        System.out.println(gfg);
        System.out.println(gfg.size());
    }
}
```

**Output**

```java
-------before removing------
{DSA=100, FANG=99, Competitive Programming=97, Problem Solving=100, Development=99, Interviews=99}
6
--------After removing-------
{}
0
```

**方法三:使用**[**removeIf()**](https://www.geeksforgeeks.org/arraylist-removeif-method-in-java/#:~:text=The%20removeIf()%20method%20of,are%20pass%20to%20the%20caller.)**方法**

**语法:**

```java
public boolean removeIf(Predicate filter)
```

**参数:**该方法采用参数**过滤器**，该过滤器代表一个谓词，该谓词为要移除的元素返回 true。

**返回:**如果谓词返回真，这个方法返回*真*，我们可以移除元素。

**异常:**如果指定的过滤器为空，该方法抛出*空指针异常*。

*   在这个方法中，您需要指定移除元素的条件，但是对于我们的情况，我们需要移除所有元素。
*   因此，我们需要迭代 entryset 中的每个键。我们将检查使用**密钥集()**方法获得的密钥集。
*   我们正在移除存在于密钥集中的 entrySet 的每个密钥。每个条目对象，1 个条目=1key+1 个值。
*   键集()给出了地图中存在的所有键。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to remove the hashings
// from HashMap using removeIf()

import java.io.*;

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        HashMap<String, Integer> gfg = new HashMap<>();

        // adding values in hashMap 1
        gfg.put("DSA", 100);
        gfg.put("Problem Solving", 100);
        gfg.put("Development", 99);
        gfg.put("Interviews", 99);
        gfg.put("Competitive Programming", 97);
        gfg.put("FANG", 99);

        System.out.println("-------before removing------");
        System.out.println(gfg);
        System.out.println(gfg.size());

        // getting all the keys of map

        Set<String> keySet = gfg.keySet();

        // checking the entry set 
        // key in keySet and remove
        // it one by one
        gfg.entrySet().removeIf(
            entry -> keySet.contains(entry.getKey()));

        System.out.println("--------After removing-------");
        System.out.println(gfg);
        System.out.println(gfg.size());
    }
}
```

**Output**

```java
-------before removing------
{DSA=100, FANG=99, Competitive Programming=97, Problem Solving=100, Development=99, Interviews=99}
6
--------After removing-------
{}
0
```
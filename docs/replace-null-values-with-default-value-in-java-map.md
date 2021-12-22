# 在 Java Map 中用默认值替换空值

> 原文:[https://www . geesforgeks . org/replace-null-values-with-default-value-in-Java-map/](https://www.geeksforgeeks.org/replace-null-values-with-default-value-in-java-map/)

给定一个包含空值的映射，任务是用默认值替换所有的空值。

**示例:**

> **输入** ： map = {1=1， 2=2， 3=0， 4=4， 5=零， 6=null}， 默认值 = 0
> **输出** ： {1=1， 2=2， 3=0， 4=4， 5=0， 6=0}
> 
> **输入** : map = {1=A，2=B，3=null，4=D，5=null，6=null}，default value =‘z’T2]输出 : {1=A，2=B，3=Z，4=D，5=Z，6=Z}

**进场:**

1.  获取具有空值和要替换的默认值的映射。
2.  使用 [Map.entrySet()方法](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/)获取地图的设置视图。
3.  使用 [stream()方法](https://www.geeksforgeeks.org/stream-in-java/)将获得的集合视图转换为流。
4.  现在借助 map()方法将空值映射为默认值。
5.  使用 Collect()方法将修改后的流收集到地图中。
6.  空值已成功替换为默认值。

下面是上述方法的实现:

**例 1:** 用整数。

```
// Java program to replace null values
// of a map with a default value

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to replace the null values
    public static <T, K> Map<K, T>
    replaceNullValues(Map<K, T> map, T defaultValue)
    {

        // Replace the null value
        map = map.entrySet()
                  .stream()
                  .map(entry -> {
                      if (entry.getValue() == null)
                          entry.setValue(defaultValue);
                      return entry;
                  })
                  .collect(Collectors.toMap(Map.Entry::getKey,
                                            Map.Entry::getValue));

        return map;
    }

    public static void main(String[] args)
    {

        // Get the map
        Map<Integer, Integer> map = new HashMap<>();
        map.put(1, 1);
        map.put(2, 2);
        map.put(3, null);
        map.put(4, 4);
        map.put(5, null);
        map.put(6, null);

        // Get the default value
        int defaultValue = 0;

        // Print the original map
        System.out.println("Map with null values: "
                           + map);

        // Replace the null values with the defaultValue
        map = replaceNullValues(map, defaultValue);

        // Print the modified map
        System.out.println("Map with null value replaced: "
                           + map);
    }
}
```

**Output:**

```
Map with null values: {1=1, 2=2, 3=null, 4=4, 5=null, 6=null}
Map with null value replaced: {1=1, 2=2, 3=0, 4=4, 5=0, 6=0}

```

**例 2:** 带字符。

```
// Java program to replace null values
// of a map with a default value

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to replace the null values
    public static <T, K> Map<K, T>
    replaceNullValues(Map<K, T> map, T defaultValue)
    {

        // Replace the null value
        map = map.entrySet()
                  .stream()
                  .map(entry -> {
                      if (entry.getValue() == null)
                          entry.setValue(defaultValue);
                      return entry;
                  })
                  .collect(Collectors.toMap(Map.Entry::getKey,
                                            Map.Entry::getValue));

        return map;
    }

    public static void main(String[] args)
    {

        // Get the map
        Map<Integer, Character> map = new HashMap<>();
        map.put(1, 'A');
        map.put(2, 'B');
        map.put(3, null);
        map.put(4, 'D');
        map.put(5, null);
        map.put(6, null);

        // Get the default value
        char defaultValue = 'Z';

        // Print the original map
        System.out.println("Map with null values: "
                           + map);

        // Replace the null values with the defaultValue
        map = replaceNullValues(map, defaultValue);

        // Print the modified map
        System.out.println("Map with null value replaced: "
                           + map);
    }
}
```

**Output:**

```
Map with null values: {1=A, 2=B, 3=null, 4=D, 5=null, 6=null}
Map with null value replaced: {1=A, 2=B, 3=Z, 4=D, 5=Z, 6=Z}

```
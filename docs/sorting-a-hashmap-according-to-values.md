# 根据值对哈希表进行排序

> 原文:[https://www . geesforgeks . org/sorting-a-hashmap-按值/](https://www.geeksforgeeks.org/sorting-a-hashmap-according-to-values/)

给定学生在学科名称是关键，得分是价值的学科中满分 100 分。我们的任务是根据值，即根据标记，对[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)进行排序。
**例:**

```
Input : Key = Math, Value = 98
        Key = Data Structure, Value = 85
        Key = Database, Value = 91
        Key = Java, Value = 95
        Key = Operating System, Value = 79
        Key = Networking, Value = 80

Output : Key = Operating System, Value = 79
         Key = Networking, Value = 80
         Key = Data Structure, Value = 85
         Key = Database, Value = 91
         Key = Java, Value = 95
         Key = Math, Value = 98
```

**解决方案:**思路是将条目集存储在一个列表中，根据值对列表进行排序。然后从列表中获取值和键，并将它们放入一个新的 hashmap 中。因此，一个新的 hashmap 根据值进行排序。
以下是上述思路的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort hashmap by values
import java.util.*;
import java.lang.*;

public class GFG {

    // function to sort hashmap by values
    public static HashMap<String, Integer> sortByValue(HashMap<String, Integer> hm)
    {
        // Create a list from elements of HashMap
        List<Map.Entry<String, Integer> > list =
               new LinkedList<Map.Entry<String, Integer> >(hm.entrySet());

        // Sort the list
        Collections.sort(list, new Comparator<Map.Entry<String, Integer> >() {
            public int compare(Map.Entry<String, Integer> o1,
                               Map.Entry<String, Integer> o2)
            {
                return (o1.getValue()).compareTo(o2.getValue());
            }
        });

        // put data from sorted list to hashmap
        HashMap<String, Integer> temp = new LinkedHashMap<String, Integer>();
        for (Map.Entry<String, Integer> aa : list) {
            temp.put(aa.getKey(), aa.getValue());
        }
        return temp;
    }

    // Driver Code
    public static void main(String[] args)
    {

        HashMap<String, Integer> hm = new HashMap<String, Integer>();

        // enter data into hashmap
        hm.put("Math", 98);
        hm.put("Data Structure", 85);
        hm.put("Database", 91);
        hm.put("Java", 95);
        hm.put("Operating System", 79);
        hm.put("Networking", 80);
        Map<String, Integer> hm1 = sortByValue(hm);

        // print the sorted hashmap
        for (Map.Entry<String, Integer> en : hm1.entrySet()) {
            System.out.println("Key = " + en.getKey() +
                          ", Value = " + en.getValue());
        }
    }
}
```

**Output**

```
Key = Operating System, Value = 79
Key = Networking, Value = 80
Key = Data Structure, Value = 85
Key = Database, Value = 91
Key = Java, Value = 95
Key = Math, Value = 98

```

**使用 Java 8 Lambdas**

这里我们将改变排序方式，使用[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)进行排序。逻辑是一样的，甚至我们也传递了比较器对象，但是只使用了 lambda。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort hashmap by values
import java.lang.*;
import java.util.*;

public class GFG {

    // function to sort hashmap by values
    public static HashMap<String, Integer>
    sortByValue(HashMap<String, Integer> hm)
    {
        // Create a list from elements of HashMap
        List<Map.Entry<String, Integer> > list
            = new LinkedList<Map.Entry<String, Integer> >(
                hm.entrySet());

        // Sort the list using lambda expression
        Collections.sort(
            list,
            (i1,
             i2) -> i1.getValue().compareTo(i2.getValue()));

        // put data from sorted list to hashmap
        HashMap<String, Integer> temp
            = new LinkedHashMap<String, Integer>();
        for (Map.Entry<String, Integer> aa : list) {
            temp.put(aa.getKey(), aa.getValue());
        }
        return temp;
    }

    // Driver Code
    public static void main(String[] args)
    {

        HashMap<String, Integer> hm
            = new HashMap<String, Integer>();

        // enter data into hashmap
        hm.put("Math", 98);
        hm.put("Data Structure", 85);
        hm.put("Database", 91);
        hm.put("Java", 95);
        hm.put("Operating System", 79);
        hm.put("Networking", 80);
        Map<String, Integer> hm1 = sortByValue(hm);

        // print the sorted hashmap
        for (Map.Entry<String, Integer> en :
             hm1.entrySet()) {
            System.out.println("Key = " + en.getKey()
                               + ", Value = "
                               + en.getValue());
        }
    }
}
```

**Output**

```
Key = Operating System, Value = 79
Key = Networking, Value = 80
Key = Data Structure, Value = 85
Key = Database, Value = 91
Key = Java, Value = 95
Key = Math, Value = 98

```

**在 Java 8 中使用流**

这里我们将使用流来对地图进行排序。我们将使用 **stream()** 方法获取 entrySet 的流，然后使用 [sorted()](https://www.geeksforgeeks.org/stream-sorted-in-java/) 方法中的 lamda 表达式对该流进行排序，最后，我们将使用 [toMap()](https://www.geeksforgeeks.org/collectors-tomap-method-in-java-with-examples/) 方法将其转换为地图。在 toMap()方法内部，我们使用 **LinkedHashMap::new** [方法引用](https://www.geeksforgeeks.org/method-references-in-java-with-examples/)来保留地图的排序顺序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort hashmap by values
import static java.util.stream.Collectors.*;

import java.lang.*;
import java.util.*;
import java.util.stream.*;
import java.util.stream.Collectors;
public class gfg3 {

    // function to sort hashmap by values
    public static HashMap<String, Integer>
    sortByValue(HashMap<String, Integer> hm)
    {
        HashMap<String, Integer> temp
            = hm.entrySet()
                  .stream()
                  .sorted((i1, i2)
                              -> i1.getValue().compareTo(
                                  i2.getValue()))
                  .collect(Collectors.toMap(
                      Map.Entry::getKey,
                      Map.Entry::getValue,
                      (e1, e2) -> e1, LinkedHashMap::new));

        return temp;
    }

    // Driver Code
    public static void main(String[] args)
    {

        HashMap<String, Integer> hm
            = new HashMap<String, Integer>();

        // enter data into hashmap
        hm.put("Math", 98);
        hm.put("Data Structure", 85);
        hm.put("Database", 91);
        hm.put("Java", 95);
        hm.put("Operating System", 79);
        hm.put("Networking", 80);
        Map<String, Integer> hm1 = sortByValue(hm);

        // print the sorted hashmap
        for (Map.Entry<String, Integer> en :
             hm1.entrySet()) {
            System.out.println("Key = " + en.getKey()
                               + ", Value = "
                               + en.getValue());
        }
    }
}
```

**Output**

```
Key = Operating System, Value = 79
Key = Networking, Value = 80
Key = Data Structure, Value = 85
Key = Database, Value = 91
Key = Java, Value = 95
Key = Math, Value = 98

```
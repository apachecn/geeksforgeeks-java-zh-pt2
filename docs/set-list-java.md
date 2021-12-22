# 在 Java 中设置为列表

> 原文:[https://www.geeksforgeeks.org/set-list-java/](https://www.geeksforgeeks.org/set-list-java/)

给定 Java 中字符串的[集合](https://www.geeksforgeeks.org/set-in-java/) ( [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 或 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) )，将其转换为字符串的列表([数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)或[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/))。

```
Input : Set hash_Set = new HashSet();
        hash_Set.add("Geeks");
        hash_Set.add("For");
Output : ArrayList or Linked List with 
         following content
         {"Geeks", "for"}

```

**方法 1(简单)**
我们简单地创建一个列表。我们遍历给定的集合，一个接一个地向列表中添加元素。

```
// Java program to demonstrate conversion of
// Set to array using simple traversal
import java.util.*;

class Test {
  public static void main(String[] args) {

    // Creating a hash set of strings
    Set<String> s = new HashSet<String>();
    s.add("Geeks");
    s.add("for");

    int n = s.size();
    List<String> aList = new ArrayList<String>(n);
    for (String x : s)
      aList.add(x);

    System.out.println("Created ArrayList is");
    for (String x : aList)
      System.out.println(x);

    // We can created LinkedList same way
  }
}
```

**Output:**

```
Created ArrayList is
Geeks
for

```

**方法 2(使用数组列表或链接列表构造函数)**

```
// Java program to demonstrate conversion of
// Set to list using constructor
import java.util.*;

class Test {
  public static void main(String[] args) {

    // Creating a hash set of strings
    Set<String> s = new HashSet<String>();
    s.add("Geeks");
    s.add("for");

    // Creating an array list using constructor
    List<String> aList = new ArrayList<String>(s);

    System.out.println("Created ArrayList is");
    for (String x : aList)
      System.out.println(x);

    System.out.println("Created LinkedList is");
    List<String> lList = new LinkedList<String>(s);      
    for (String x : lList)
      System.out.println(x);      
  }
}
```

**Output:**

```
Created ArrayList is
Geeks
for
Created LinkedList is
Geeks
for

```

**方法 3(使用 addAll 方法)**

```
// Java program to demonstrate conversion of
// Set to array using addAll() method.
import java.util.*;

class Test {
  public static void main(String[] args) {

    // Creating a hash set of strings
    Set<String> s = new HashSet<String>();
    s.add("Geeks");
    s.add("for");

    List<String> aList = new ArrayList<String>();
    aList.addAll(s);

    System.out.println("Created ArrayList is");
    for (String x : aList)
      System.out.println(x);

    List<String> lList = new LinkedList<String>();
    lList.addAll(s);

    System.out.println("Created LinkedList is");
    for (String x : lList)
      System.out.println(x);      
  }
}
```

**Output:**

```
Created ArrayList is
Geeks
for
Created LinkedList is
Geeks
for

```

**方法 4(使用 Java 中的[流](https://www.geeksforgeeks.org/stream-in-java/) )**
我们使用 Java 中的[流](https://www.geeksforgeeks.org/stream-in-java/)将给定集合转换为蒸汽，然后流至列表。这仅适用于 Java 8 或之后的版本。

```
// Java program to demonstrate conversion of
// Set to list using stream
import java.util.*;
import java.util.stream.*;

class Test {
  public static void main(String[] args) {

    // Creating a hash set of strings
    Set<String> s = new HashSet<String>();
    s.add("Geeks");
    s.add("for");

    List<String> aList = s.stream().collect(Collectors.toList());

    for (String x : aList)
      System.out.println(x);
  }
}
```

**Output:**

```
Geeks
for

```
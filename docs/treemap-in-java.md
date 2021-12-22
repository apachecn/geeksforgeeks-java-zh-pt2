# Java 中的树形图

> 原文:[https://www.geeksforgeeks.org/treemap-in-java/](https://www.geeksforgeeks.org/treemap-in-java/)

Java 中的 TreeMap 与 AbstractMap 类一起用于实现[地图接口](https://www.geeksforgeeks.org/map-interface-java-examples/)和[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)。地图根据其键的自然顺序进行排序，或者通过地图创建时提供的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)进行排序，具体取决于使用的构造函数。这被证明是排序和存储键值对的有效方式。树图维护的存储顺序必须和其他排序图一样与 equals 一致，而不考虑显式比较器。如果多个线程同时访问一个映射，并且至少有一个线程在结构上修改了该映射，那么树映射实现就不是同步的，它必须在外部同步。

![](img/41cbdf7be059b1242e0182afb1381bc9.png)

## 树形图的特征

树形图的一些重要特征如下:

1.  这个类是 [Java 集合](https://www.geeksforgeeks.org/collections-in-java-2/)框架的成员。
2.  该类实现了包括[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)、[排序地图](https://www.geeksforgeeks.org/sortedmap-java-examples/)在内的[地图接口](https://www.geeksforgeeks.org/map-interface-java-examples/)，并扩展了抽象地图类。
3.  Java 中的 TreeMap 不允许空键(像 Map)，因此会抛出 [NullPointerException](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) 。但是，多个空值可以与不同的键相关联。
4.  此类及其视图中的方法返回的条目对表示生成映射时的快照。他们不支持 [Entry.setValue](https://www.geeksforgeeks.org/map-entry-interface-java-example/) 方法。

现在让我们坚持向前，讨论同步树图。树图的实现不同步。这意味着，如果多个线程同时访问一个树集合，并且至少有一个线程修改了该集合，那么它必须在外部同步。这通常通过使用[collections . synchronizedstortedmap](https://www.geeksforgeeks.org/collections-synchronizedsortedmap-method-in-java-with-examples/)方法来完成。这最好在创建时完成，以防止对集合的意外非同步访问。这可以通过以下方式实现:

```
SortedMap m = Collections.synchronizedSortedMap(new TreeMap(...)); 
```

极客们，现在你们一定想知道 TreemMap 在内部是如何工作的？

树映射中的方法在获取键集和值时，返回一个本质上快速失败的迭代器。因此，任何并发修改都会引发[并发修改异常](https://www.geeksforgeeks.org/concurrentmodificationexception-in-java-with-examples/)。树形图是基于红-黑[树](https://www.geeksforgeeks.org/red-black-tree-set-1-introduction-2/)数据结构。

**树中每个节点都有:**

*   3 个变量( *K 键=键，V 值=值，布尔颜色=颜色*)
*   3 个引用(*条目左=左，条目右=右，条目父=父*)

## 树形图中的构造函数

为了创建一个树形图，我们需要创建一个树形图类的对象。树图类由各种构造函数组成，这些构造函数允许创建树图。以下是此类中可用的构造函数:

1.  树状目录()
2.  树形图(比较器组件)
3.  树图(地图 m)
4.  TreeMap(黑色文件夹 sm)

让我们在实现每个构造函数的同时单独讨论它们，如下所示:

**构造函数 1:** 树形图()

此构造函数用于构建一个空的树图，该树图将使用其键的自然顺序进行排序。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate TreeMap
// using the Default Constructor

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Main class
// TreeMapImplementation
public class GFG {

    // Method 1
    // To show TreeMap constructor
    static void Example1stConstructor()
    {
        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Printing the elements of TreeMap
        System.out.println("TreeMap: " + tree_map);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        System.out.println("TreeMap using "
                           + "TreeMap() constructor:\n");

        // Calling constructor
        Example1stConstructor();
    }
}
```

**Output:** 

```
TreeMap using TreeMap() constructor:
TreeMap: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
```

**构造器 2:** 树形图(比较器组件)

此构造函数用于构建一个空的 TreeMap 对象，其中的元素需要排序顺序的外部规范。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate TreeMap
// using Comparator Constructor

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Class 1
// Helper class representing Student
class Student {

    // Attributes of a student
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name, String address)
    {

        // This keyword refers to current object itself
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Method of this class
    // To print student details
    public String toString()
    {
        return this.rollno + " " + this.name + " "
            + this.address;
    }
}

// Class 2
// Helper class - Comparator implementattion
class Sortbyroll implements Comparator<Student> {

    // Used for sorting in ascending order of
    // roll number
    public int compare(Student a, Student b)
    {
        return a.rollno - b.rollno;
    }
}

// Class 3
// Main class
public class GFG {

    // Calling constructor inside main()
    static void Example2ndConstructor()
    {
        // Creating an empty TreeMap
        TreeMap<Student, Integer> tree_map
            = new TreeMap<Student, Integer>(
                new Sortbyroll());

        // Mapping string values to int keys
        tree_map.put(new Student(111, "bbbb", "london"), 2);
        tree_map.put(new Student(131, "aaaa", "nyc"), 3);
        tree_map.put(new Student(121, "cccc", "jaipur"), 1);

        // Printing the elements of TreeMap
        System.out.println("TreeMap: " + tree_map);
    }

    // Main driver method
    public static void main(String[] args)
    {

        System.out.println("TreeMap using "
                           + "TreeMap(Comparator)"
                           + " constructor:\n");
        Example2ndConstructor();
    }
}
```

**Output:** 

```
TreeMap using TreeMap(Comparator) constructor:
TreeMap: {111 bbbb london=2, 121 cccc jaipur=1, 131 aaaa nyc=3}
```

**构造函数 3:** 树形图(图 M)

这个构造函数用来初始化一个树形图，这个树形图中的条目来自给定的映射 M，这个映射 M 将使用关键字的自然顺序进行排序。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate TreeMap
// using the Default Constructor

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Main class
public class TreeMapImplementation {

    // Method 1
    // To illustrate constructor<Map>
    static void Example3rdConstructor()
    {
        // Creating an empty HashMap
        Map<Integer, String> hash_map
            = new HashMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Creating the TreeMap using the Map
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>(hash_map);

        // Printing the elements of TreeMap
        System.out.println("TreeMap: " + tree_map);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        System.out.println("TreeMap using "
                           + "TreeMap(Map)"
                           + " constructor:\n");

        Example3rdConstructor();
    }
}
```

**Output:** 

```
TreeMap using TreeMap(Map) constructor:
TreeMap: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
```

**构造函数 4:** 树形图(SortedMap sm)

该构造函数用于初始化一个树形图，其条目来自给定的[排序图](https://www.geeksforgeeks.org/sortedmap-java-examples/)，这些条目将以与给定排序图相同的顺序存储。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate TreeMap
// using the SortedMap Constructor

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Main class
// TreeMapImplementation
public class GFG {

    // Method
    // To show TreeMap(SortedMap) constructor
    static void Example4thConstructor()
    {
        // Creating a SortedMap
        SortedMap<Integer, String> sorted_map
            = new ConcurrentSkipListMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        sorted_map.put(10, "Geeks");
        sorted_map.put(15, "4");
        sorted_map.put(20, "Geeks");
        sorted_map.put(25, "Welcomes");
        sorted_map.put(30, "You");

        // Creating the TreeMap using the SortedMap
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>(sorted_map);

        // Printing the elements of TreeMap
        System.out.println("TreeMap: " + tree_map);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        System.out.println("TreeMap using "
                           + "TreeMap(SortedMap)"
                           + " constructor:\n");

        Example4thConstructor();
    }
}
```

**Output:** 

```
TreeMap using TreeMap(SortedMap) constructor:
TreeMap: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
```

## 树图类中的方法

<figure class="table">

| 方法 | 已执行的操作 |
| --- | --- |
| [晴()](https://www.geeksforgeeks.org/treemap-clear-method-in-java/) | 该方法从此树映射中移除所有映射，并清除该映射。 |
| [克隆()](https://www.geeksforgeeks.org/treemap-clone-method-in-java/) | 该方法返回该树形图的一个浅层副本。 |
| [包含键(对象键)](https://www.geeksforgeeks.org/treemap-containskey-method-in-java/) | 如果此映射包含指定键的映射，则返回 true。 |
| [包含值(对象值)](https://www.geeksforgeeks.org/treemap-containsvalue-method-in-java/) | 如果此映射将一个或多个键映射到指定值，则返回 true。 |
| [输入 ySet()](https://www.geeksforgeeks.org/treemap-entryset-method-in-java/) | 返回此映射中包含的映射的集合视图。 |
| [firstKey()](https://www.geeksforgeeks.org/java-util-treemap-firstentry-firstkey-java/) | 返回当前排序地图中的第一个(最低的)键。 |
| [获取(对象键)](https://www.geeksforgeeks.org/treemap-get-method-in-java/) | 返回此映射映射到指定键的值。 |
| [头标(对象键值)](https://www.geeksforgeeks.org/treemap-headmap-method-in-java/) | 方法返回严格小于参数 key_value 的映射部分的视图。 |
| [键集()](https://www.geeksforgeeks.org/treemap-keyset-method-in-java/) | 方法返回树图中包含的键的集合视图。 |
| [负载力()](https://www.geeksforgeeks.org/treemap-lastkey-method-in-java/) | 返回当前排序地图中的最后一个(最高的)键。 |
| [放(对象键，对象值)](https://www.geeksforgeeks.org/treemap-put-method-in-java/) | 方法用于将映射插入到地图中。 |
| [普塔尔(地图地图)](https://www.geeksforgeeks.org/treemap-putall-method-in-java/) | 将指定映射中的所有映射复制到此映射。 |
| [移除(对象键)](https://www.geeksforgeeks.org/treemap-remove-method-in-java/) | 从该树映射中删除该键的映射(如果存在)。 |
| [尺寸()](https://www.geeksforgeeks.org/treemap-size-method-in-java/) | 返回此映射中键值映射的数量。 |
| [皮下(k 起始元件，k 结束元件)](https://www.geeksforgeeks.org/treemap-submap-method-in-java/) | 该方法返回该映射的部分，其键的范围从 startKey(包含)到 endKey(不包含)。 |
| [值()](https://www.geeksforgeeks.org/treemap-values-method-in-java/) | 返回此地图中包含的值的集合视图。 |

</figure>

**实现:**下面的程序将更好地演示如何创建、插入和遍历树形图。

插图:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Operations in TreeMap
// Such as Creation, insertion
// searching, and traversal

// Importing required classes
import java.util.*;
import java.util.concurrent.*;

// Main class
// Implementation of TreeMap
public class GFG {

    // Declaring a TreeMap
    static TreeMap<Integer, String> tree_map;

    // Method 1
    // To create TreeMap
    static void create()
    {

        // Creating an empty TreeMap
        tree_map = new TreeMap<Integer, String>();

        // Display message only
        System.out.println("TreeMap successfully"
                           + " created");
    }

    // Method 2
    // To Insert values in the TreeMap
    static void insert()
    {

        // Mapping string values to int keys
        // using put() method
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Display message only
        System.out.println("\nElements successfully"
                           + " inserted in the TreeMap");
    }

    // Method 3
    // To search a key in TreeMap
    static void search(int key)
    {

        // Checking for the key
        System.out.println("\nIs key \"" + key
                           + "\" present? "
                           + tree_map.containsKey(key));
    }

    // Method 4
    // To search a value in TreeMap
    static void search(String value)
    {

        // Checking for the value
        System.out.println("\nIs value \"" + value
                           + "\" present? "
                           + tree_map.containsValue(value));
    }

    // Method 5
    // To display the elements in TreeMap
    static void display()
    {

        // Displaying the TreeMap
        System.out.println("\nDisplaying the TreeMap:");

        System.out.println("TreeMap: " + tree_map);
    }

    // Method 6
    // To traverse TreeMap
    static void traverse()
    {

        // Display message only
        System.out.println("\nTraversing the TreeMap:");

        for (Map.Entry<Integer, String> e :
             tree_map.entrySet())
            System.out.println(e.getKey() + " "
                               + e.getValue());
    }

    // Method 6
    // Main driver method
    public static void main(String[] args)
    {

        // Calling above defined methods inside main()

        // Creating a TreeMap
        create();

        // Inserting the values in the TreeMap
        insert();

        // Search key "50" in the TreeMap
        search(50);

        // Search value "Geeks" in the TreeMap
        search("Geeks");

        // Display the elements in TreeMap
        display();

        // Traversing the TreeMap
        traverse();
    }
}
```

**Output:** 

```
TreeMap successfully created
Elements successfully inserted in the TreeMap
Is key "50" present? false
Is value "Geeks" present? true
Displaying the TreeMap:
TreeMap: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Traversing the TreeMap:
10 Geeks
15 4
20 Geeks
25 Welcomes
30 You
```

## 在树形图上执行各种操作

在 Java 1.5 中引入泛型之后，可以限制可以存储在 TreeMap 中的对象类型。现在，让我们看看如何在 TreeMap 上执行一些常用的操作。

**操作 1:** 添加元素

为了给树形图增加一个元素，我们可以使用 [put()方法](https://www.geeksforgeeks.org/treemap-put-method-in-java/?ref=rp)。但是，插入顺序不会保留在树形图中。在内部，对于每个元素，键都是按升序进行比较和排序的。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Addition of Elements
// in TreeMap using put() Method

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Default Initialization of a TreeMap
        TreeMap tm1 = new TreeMap();

        // Inserting the elements in TreeMap
        // using put() method
        tm1.put(3, "Geeks");
        tm1.put(2, "For");
        tm1.put(1, "Geeks");

        // Initialization of a TreeMap using Generics
        TreeMap<Integer, String> tm2
            = new TreeMap<Integer, String>();

        // Inserting the elements in TreeMap
        // again using put() method
        tm2.put(new Integer(3), "Geeks");
        tm2.put(new Integer(2), "For");
        tm2.put(new Integer(1), "Geeks");

        // Printing the elements of both TreeMaps

        // Map 1
        System.out.println(tm1);
        // Map 2
        System.out.println(tm2);
    }
}
```

**Output:** 

```
{1=Geeks, 2=For, 3=Geeks}
{1=Geeks, 2=For, 3=Geeks}
```

**操作 2:更换元件**

添加元素后，如果我们想改变元素，可以通过 [put()方法](https://www.geeksforgeeks.org/treemap-put-method-in-java/?ref=rp)再次添加元素来完成。由于树图中的元素是使用键来索引的，因此只需插入我们想要更改的键的更新值，就可以更改键的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate Updation of Elements
// in TreeMap using put() Method

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Initialization of a TreeMap
        // using Generics
        TreeMap<Integer, String> tm
            = new TreeMap<Integer, String>();

        // Inserting the elements in Map
        // using put() method
        tm.put(3, "Geeks");
        tm.put(2, "Geeks");
        tm.put(1, "Geeks");

        // Print all current elements in map
        System.out.println(tm);

        // Inserting the element at specified
        // corresponding to specified key
        tm.put(2, "For");

        // Printing the updated elements of Map
        System.out.println(tm);
    }
}
```

**Output:** 

```
{1=Geeks, 2=Geeks, 3=Geeks}
{1=Geeks, 2=For, 3=Geeks}
```

**操作 3:** 移除元素

为了从树形图中移除一个元素，我们可以使用[移除()方法](https://www.geeksforgeeks.org/treemap-remove-method-in-java/?ref=rp)。此方法获取键值，并从该树映射中移除该键的映射(如果它存在于该映射中)。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate Removal of Elements
// in TreeMap using remove() Method

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Initialization of a TreeMap
        // using Generics
        TreeMap<Integer, String> tm
            = new TreeMap<Integer, String>();

        // Inserting the elements
        // using put() method
        tm.put(3, "Geeks");
        tm.put(2, "Geeks");
        tm.put(1, "Geeks");
        tm.put(4, "For");

        // Printing all elements of Map
        System.out.println(tm);

        // Removing the element corresponding to key
        tm.remove(4);

        //  Printing updated TreeMap
        System.out.println(tm);
    }
}
```

**Output:** 

```
{1=Geeks, 2=Geeks, 3=Geeks, 4=For}
{1=Geeks, 2=Geeks, 3=Geeks}
```

**操作 4:** 遍历树形图

有多种方法可以迭代地图。最著名的方法是对每个循环使用一个并获取密钥。使用 *getValue()方法*找到密钥的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Iterating over TreeMap
// using

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Initialization of a TreeMap
        // using Generics
        TreeMap<Integer, String> tm
            = new TreeMap<Integer, String>();

        // Inserting the elements
        // using put() method
        tm.put(3, "Geeks");
        tm.put(2, "For");
        tm.put(1, "Geeks");

        // For-each loop for traversal over Map
        // via entrySet() Method
        for (Map.Entry mapElement : tm.entrySet()) {

            int key = (int)mapElement.getKey();

            // Finding the value
            String value = (String)mapElement.getValue();

            // Printing the key and value
            System.out.println(key + " : " + value);
        }
    }
}
```

**Output:** 

```
1 : Geeks
2 : For
3 : Geeks
```
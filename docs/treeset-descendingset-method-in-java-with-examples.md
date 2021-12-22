# Java 中的 TreeSet descendingSet()方法，示例

> 原文:[https://www . geeksforgeeks . org/treeset-dependingset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treeset-descendingset-method-in-java-with-examples/)

[**Java . util . treeset<E>**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)类的 **descendingSet()** 方法用于返回该集合中包含的元素的逆序视图。该集合支持降序集合，因此对该集合的更改会反映在降序集合中，反之亦然。如果在任一集合上进行迭代时修改了任一集合(通过迭代器自己的移除操作除外)，迭代的结果是未定义的。
返回的集合具有相当于 Collections.reverseOrder(比较器())的排序。表达式 s.descendingSet()。descendingSet()返回 s 的视图，本质上等同于 s。
**语法:**

```
public NavigableSet descendingSet()
```

**返回值:**该方法返回该集合的一个**逆序视图**。
以下是举例说明*下降集()*方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// descendingSet() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // create tree set object
            TreeSet<String> treeadd = new TreeSet<String>();

            // populate the TreeSet using add() method
            treeadd.add("A");
            treeadd.add("B");
            treeadd.add("C");
            treeadd.add("D");

            // Print the TreeSet
            System.out.println("TreeSet: " + treeadd);

            // getting the reverse order view of element
            // using descendingSet() method
            NavigableSet<String>
                treereverse = treeadd.descendingSet();

            // getting iterated view of NavigableSet
            Iterator<String> iterator = treereverse.iterator();

            System.out.println("\nValues using DescendingSet:");

            // printing the integrated value
            while (iterator.hasNext()) {
                System.out.println("Value : "
                                   + iterator.next());
            }
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
TreeSet: [A, B, C, D]

Values using DescendingSet:
Value : D
Value : C
Value : B
Value : A
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// descendingSet() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // create tree set object
            TreeSet<Integer> treeadd = new TreeSet<Integer>();

            // populate the TreeSet using add() method
            treeadd.add(10);
            treeadd.add(20);
            treeadd.add(30);
            treeadd.add(40);

            // getting the reverse order view of element
            // using descendingSet() method
            NavigableSet<Integer> treereverse = treeadd.descendingSet();

            // getting iterated view of NavigableSet
            Iterator<Integer> iterator = treereverse.iterator();

            System.out.println("\nValues using DescendingSet:");

            // printing the integrated value
            while (iterator.hasNext()) {
                System.out.println("Value : " + iterator.next());
            }
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Values using DescendingSet:
Value : 40
Value : 30
Value : 20
Value : 10
```
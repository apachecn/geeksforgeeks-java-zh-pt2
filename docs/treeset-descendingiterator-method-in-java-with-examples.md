# Java 中的 TreeSet descendingIterator()方法，示例

> 原文:[https://www . geeksforgeeks . org/treeset-dependingiterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treeset-descendingiterator-method-in-java-with-examples/)

[**Java . util . treeset<【E】>**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)类的**Degending Terrar()**方法用于以降序返回该集合中元素的迭代器。
**语法:**

```java
public Iterator descendingIterator()
```

**返回值:**这个方法以降序返回这个集合中元素的迭代器。
以下是举例说明*下降法*方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// descendingIterator() method
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

            // Print the TreeSet
            System.out.println("TreeSet: " + treeadd);

            // create descending iterator
            // using descendingIterator() method
            Iterator<Integer>
                iterator = treeadd.descendingIterator();

            System.out.println("\nValues using DescendingIterator:");

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

```java
TreeSet: [10, 20, 30, 40]

Values using DescendingIterator:
Value : 40
Value : 30
Value : 20
Value : 10
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// descendingIterator() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
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

            // create descending iterator
            // using descendingIterator() method
            Iterator<String>
                iterator = treeadd.descendingIterator();

            System.out.println("\nValues using DescendingIterator:");

            // printing the integrated value
            while (iterator.hasNext()) {
                System.out.println("Value : "
                                   + iterator.next());
            }
        }

        catch (Exception e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
TreeSet: [A, B, C, D]

Values using DescendingIterator:
Value : D
Value : C
Value : B
Value : A
```
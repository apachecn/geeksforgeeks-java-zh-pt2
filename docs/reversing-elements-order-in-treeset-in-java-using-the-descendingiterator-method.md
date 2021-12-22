# 在 Java 中使用降级畸胎方法反转树集中的元素顺序

> 原文:[https://www . geeksforgeeks . org/reversing-elements-order-in-treeset-in-Java-using-dependingiterator-method/](https://www.geeksforgeeks.org/reversing-elements-order-in-treeset-in-java-using-the-descendingiterator-method/)

[**Java . util . treeset<E>**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)类的**Degending Terrar()**方法用于以降序返回集合中元素的迭代器。一旦迭代器用 descendingIterator()的返回值赋值，就使用 while 循环迭代迭代器。

**示例:**

```java
Input : TreeSet = [2, 5, 6]
Output: Reverse = [6, 5, 2]

Input : TreeSet = [a, b, c]
Output: Reverse = 
```

**语法:**

```java
public Iterator descendingIterator()
```

**返回值:**这个方法以降序返回这个集合中元素的迭代器。

**进场:**

1.  创建一个迭代器变量，并用 descendingIterator()方法的返回值初始化它。
2.  使用 while 循环迭代迭代器变量。
3.  在循环过程中打印数值。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Reversing Elements Order in TreeSet in
// Java Using the descendingIterator Method
import java.util.Iterator;
import java.util.TreeSet;

class GFG {
    public static void main(String[] args)
    {

        // Creating TreeSet and adding value to it
        TreeSet<Integer> setOfNumbers
            = new TreeSet<Integer>();

        setOfNumbers.add(2);
        setOfNumbers.add(5);
        setOfNumbers.add(1);
        setOfNumbers.add(7);
        setOfNumbers.add(4);

        // Printing TreeSet Elements
        System.out.println("TreeSet(setOfNumbers) : "
                           + setOfNumbers);

        Iterator<Integer> iterator
            = setOfNumbers.descendingIterator();

        // Iterating TreeSet
        System.out.print("TreeSet in reverse order : ");

        while (iterator.hasNext()) {
            System.out.print(iterator.next() + " ");
        }
    }
}
```

**Output**

```java
TreeSet(setOfNumbers) : [1, 2, 4, 5, 7]
TreeSet in reverse order : 7 5 4 2 1
```
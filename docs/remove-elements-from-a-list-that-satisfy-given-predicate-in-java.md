# 从列表中移除满足 Java 中给定谓词的元素

> 原文:[https://www . geeksforgeeks . org/remove-elements-from-list-the-to-self-given-predicate-in-Java/](https://www.geeksforgeeks.org/remove-elements-from-a-list-that-satisfy-given-predicate-in-java/)

以下是从满足谓词条件的列表中有效移除元素的方法:

```java
p  ==> Predicate, specifying the condition
l  ==> List, from which element to be removed

```

### 使用迭代器

下面的程序演示了使用谓词
从列表中移除空元素

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to remove nulls
// from a List using iterator and Predicate
import java.util.function.Predicate;
import java.util.*;

class GFG {

    // Generic function to remove Null Using Iterator
    public static <T> List<T>
    removeNullUsingIterator(List<T> l, Predicate<T> p)
    {

        // Create an iterator from the l
        Iterator<T> itr = l.iterator();

        // Find and remove all null
        while (itr.hasNext()) {

            // Fetching the next element
            T t = itr.next();

            // Checking for Predicate condition
            if (!p.test(t)) {

                // If the condition matches,
                // remove that element
                itr.remove();
            }
        }

        // Return the null
        return l;
    }

    public static void main(String[] args)
    {

        // Create the l with null values
        List<String> l = new ArrayList<>(
               Arrays.asList("Geeks",
                             null,
                             "forGeeks",
                             null,
                             "A computer portal"));

        // Print the list
        System.out.println("List with null values: " + l);

        // Creating a Predicate condition checking for null
        Predicate<String> isNull = item -> Objects.nonNull(item);

        // Removing nulls using iterator and Predicate
        l = removeNullUsingIterator(l, isNull);

        // Print the list
        System.out.println("List with null values removed: " + l);
    }
}
```

**Output**

```java
List with null values: [Geeks, null, forGeeks, null, A computer portal]
List with null values removed: [Geeks, forGeeks, A computer portal]

```
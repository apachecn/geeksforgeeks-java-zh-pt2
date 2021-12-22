# 哪些数据类型不能存储在 Java 数组列表中？

> 原文:[https://www . geesforgeks . org/哪些数据类型不能存储在 java-arraylist/](https://www.geeksforgeeks.org/which-data-type-cannot-be-stored-in-java-arraylist/)

数组列表类实现了一个可增长的对象数组。ArrayList 不能包含基本数据类型，如 int、double、char 和 long。介绍了 java 中用于保存原始数据值的包装类。这些类型的对象持有它们对应的基元类型的一个值(int、double、short、byte)。当 java 结构中使用需要对象的原始数据类型时，使用它们，例如[jlist](https://www.geeksforgeeks.org/java-swing-jlist-with-examples/)、[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/)。现在，为了在数组列表中保存像 int 和 char 这样的原始数据，我们来解释一下。

***原始数据类型不能存储在数组列表中，但可以存储在数组*** 中。数组列表是一种列表，列表实现了集合接口。集合容器只需要对象数据类型，集合中完成的所有操作(如迭代)只能在对象上执行，而不能在基本数据类型上执行。数组列表不能存储整数。要在数组列表中放置整数，我们必须将它们转换为整数。这可以在 ArrayList 上的 add()方法中完成。每个 int 必须单独添加。

**病例:**

1.  数组列表中的整数
2.  数组列表中的字符

**情况 1:** 数组列表中的整数

要在数组列表中放置 int，首先，它们被转换成整数。这可以在 ArrayList 上的 add 方法中完成。每个 int 必须单独添加。例如，考虑一个 int 数组。它有 3 个值。我们创建一个数组列表，并在 for 循环中将这些整数作为整数相加。

add()方法接收一个整数。我们可以将一个 int 传递给这个方法——这个 int 被转换成一个 Integer。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program that uses ArrayList of Integer Values

// Importing ArrayList class from
// java.util package
import java.util.ArrayList;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create and insert custom elements in array
        int[] ids = { -3, 0, 100 };

        // Create ArrayList of Integer type
        ArrayList<Integer> values = new ArrayList<>();

        // For- each loop to iterate over ArrayList
        for (int id : ids) {

            // Add all the ints as Integers with add()
            // method, here the ints are cast to Integer
            // implicitly.
            values.add(id);
        }

        System.out.println(values);

        // The collections have the same lengths
        System.out.println(values.size());

        System.out.println(ids.length);
    }
}
```

**Output**

```java
[-3, 0, 100]
3
3
```

**使用 toArray 方法–**to array 方法将数组列表的元素复制到数组中。

一个返回一个对象数组，需要强制转换。然而，这个版本返回一个类型化数组。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing List and ArrayList class of
// java.util package 
import java.util.ArrayList;
import java.util.List;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating and initializing ArrayList
        ArrayList<Integer> list = new ArrayList<>();

        // Adding elements to ArrayList
        // Custom inputs
        list.add(7);
        list.add(8);
        list.add(9);

        // Create an empty array and pass to toArray.
        Integer[] array = {};

        // Converting above array to ArrayList
        // using inbuilt method - list.toArray(array)
        array = list.toArray(array);

        // Iterating over elements using for-each loop over
        // elements of ArrayList derived from initial array
        for (int elem : array) {

            // Printing elements of converted ArrayList
            System.out.println(elem);
        }
    }
}
```

**Output**

```java
7
8
9
```

**案例 2** :数组列表中的字符

在 Java 数组列表中，字符用例是:

*   将它们转换成字符
*   将字符串值转换为字符数组列表。

**示例:**将字符串转换为字符列表的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program showcasing where Data Type
// can not be stored in ArrayList

// Case 2: Java Program to convert a string
// to a list of characters

// Importing List and ArrayList classes from
// java.util package
import java.util.ArrayList;
import java.util.List;

// Class - Convert a String to a List of Characters
class GFG

{
    // Main driver method
    public static void main(String[] args)

    {
        // Custom string
        String string = "Geeks for Geeks";

        List<Character> chars = new ArrayList<>();

        for (char ch : string.toCharArray()) {

            chars.add(ch);
        }

        System.out.println(chars);
    }
}
```

**Output**

```java
[G, e, e, k, s,  , f, o, r,  , G, e, e, k, s]
```
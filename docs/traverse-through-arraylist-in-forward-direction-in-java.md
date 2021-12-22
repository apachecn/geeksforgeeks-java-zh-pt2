# 在 Java 中向前遍历数组列表

> 原文:[https://www . geesforgeks . org/traverse-through-ArrayList-in-forward-in-Java/](https://www.geeksforgeeks.org/traverse-through-arraylist-in-forward-direction-in-java/)

[**ArrayList**](https://www.geeksforgeeks.org/arraylist-in-java/) 是集合框架的一部分，存在于 java.util 包中。它为我们提供了 Java 中的动态数组。java.util.ArrayList 类的 listIterator()方法用于返回列表中元素的列表迭代器(以适当的顺序)。数组列表可以通过多种方式向前遍历。

**例:**

```
Input : ArrayList: [5, 6, 8, 10]
Output:
Value is : 5
Value is : 6
Value is : 8
Value is : 10
```

**方法 1:使用列表迭代器方法**

1.  Creates a list iterator object for a given array list.
2.  Use the while loop with the condition that hasNext () method is used.
3.  If the hasNext () method returns false, the loop is interrupted.
4.  Otherwise, use the object.next () method to print the value.

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Traverse through ArrayList in
// forward direction using Java
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<Integer> alist = new ArrayList<>();

        // adding element to arrlist
        alist.add(5);
        alist.add(6);
        alist.add(8);
        alist.add(10);

        ListIterator<Integer> it = alist.listIterator();

        while (it.hasNext()) {
            System.out.println("Value is : " + it.next());
        }
    }
}
```

**Output**

```
Value is : 5
Value is : 6
Value is : 8
Value is : 10
```

**时间复杂度:** O(N)，其中 N 是数组列表的长度。

**方法 2:用于循环**

使用 for 循环打印数组列表中的所有值。数组列表的大小可以使用 ArrayList.size()方法获得，访问元素可以使用 ArrayList.get()方法。

实现:

## Java

```
// Traverse through ArrayList in
// forward direction using Java
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<Integer> alist = new ArrayList<>();

        // adding element to arrlist
        alist.add(5);
        alist.add(6);
        alist.add(8);
        alist.add(10);

        for (int i = 0; i < alist.size(); i++)
            System.out.println("Value is : "
                               + alist.get(i));
    }
}
```

**输出**

```
Value is : 5
Value is : 6
Value is : 8
Value is : 10
```

**时间复杂度:** O(N)，其中 N 是数组列表的长度。

**方法 3:使用 forEach 循环**

使用每个循环打印数组列表中的所有值。

**示例:**

## Java

```
// Traverse through ArrayList in
// forward direction using Java
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<Integer> alist = new ArrayList<>();

        // adding element to arrlist
        alist.add(5);
        alist.add(6);
        alist.add(8);
        alist.add(10);

        for (Integer i : alist)
            System.out.println("Value is : " + i);
    }
}
```

**输出**

```
Value is : 5
Value is : 6
Value is : 8
Value is : 10
```

**时间复杂度:** O(N)，其中 N 是数组列表的长度。

**方法 4:使用λ函数**

使用 lambda 函数打印数组列表中的所有值。

**示例:**

## Java

```
// Traverse through ArrayList in
// forward direction using Java
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<Integer> alist = new ArrayList<>();

        // adding element to arrlist
        alist.add(5);
        alist.add(6);
        alist.add(8);
        alist.add(10);
        // lambda
        alist.forEach(
            i -> System.out.println("Value is : " + i));
    }
}
```

**输出**

```
Value is : 5
Value is : 6
Value is : 8
Value is : 10
```

**时间复杂度:** O(N)，其中 N 是数组列表的长度。
# Java 中的 Stream min()方法，示例

> 原文:[https://www . geesforgeks . org/stream-min-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stream-min-method-in-java-with-examples/)

**Stream.min()** 根据提供的比较器返回流的最小元素。比较器是一个比较函数，它对一些对象集合进行总排序。min()是一个 ***终端操作*** ，结合流元素，返回汇总结果。所以，min()是归约的特例。该方法返回可选实例。

**语法:**

```
Optional<T> min(Comparator<? super T> comparator)

Where, Optional is a container object which
may or may not contain a non-null value 
and T is the type of objects
that may be compared by this comparator

```

**异常:**如果最小元素为空，该方法抛出 ***空指针异常*** 。

**示例 1 :** 整数列表中的最小值。

```
// Java code for Stream.min() method to get
// the minimum element of the Stream
// according to the provided Comparator.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = Arrays.asList(-9, -18, 0, 25, 4);

        // Using stream.min() to get minimum
        // element according to provided Integer Comparator
        Integer var = list.stream().min(Integer::compare).get();

        System.out.print(var);
    }
}
```

输出:

```
-18

```

**例 2 :** 使用 min()函数反向比较器获取最大值。

```
// Java code for Stream.min() method
// to get the minimum element of the 
// Stream according to provided comparator.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = Arrays.asList(-9, -18, 0, 25, 4);

        // Using Stream.min() with reverse
        // comparator to get maximum element.
        Optional<Integer> var = list.stream()
                    .min(Comparator.reverseOrder());

        // IF var is empty, then output will be Optional.empty
        // else value in var is printed.
        if(var.isPresent()){
        System.out.println(var.get());
        }
        else{
            System.out.println("NULL");
        }

    }
}
```

输出:

```
25

```

**示例 3 :** 基于最后一个字符比较字符串。

```
// Java code for Stream.min() method
// to get the minimum element of the 
// Stream according to provided comparator.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating an array of strings
        String[] array = { "Geeks", "for", "GeeksforGeeks",
                           "GeeksQuiz" };

        // The Comparator compares the strings
        // based on their last characters and returns
        // the minimum value accordingly.
        Optional<String> MIN = Arrays.stream(array).min((str1, str2) -> 
                    Character.compare(str1.charAt(str1.length() - 1), 
                                      str2.charAt(str2.length() - 1)));

        // If a value is present,
        // isPresent() will return true
        if (MIN.isPresent()) 
            System.out.println(MIN.get()); 
        else
            System.out.println("-1"); 
    }
}
```

输出:

```
for

```
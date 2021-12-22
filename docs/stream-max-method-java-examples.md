# Java 中的 Stream.max()方法，示例

> 原文:[https://www . geesforgeks . org/stream-max-method-Java-examples/](https://www.geeksforgeeks.org/stream-max-method-java-examples/)

Stream.max()根据提供的比较器返回流的最大元素。比较器是一个比较函数，它对一些对象集合进行总排序。max()是一个终端操作，它组合流元素并返回一个汇总结果。所以，max()是归约的特例。该方法返回可选实例。

**语法:**

```java
Optional<T> max(Comparator<? super T> comparator)

Where, Optional is a container object which
may or may not contain a non-null value 
and T is the type of objects
that may be compared by this comparator

```

**异常:**如果最大元素为空，该方法抛出 ***空指针异常*** 。

**例 1 :**

```java
// Implementation of Stream.max()
// to get the maximum element
// of the Stream according to the
// provided Comparator.
import java.util.*;
import java.util.Optional;
import java.util.Comparator;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = Arrays.asList(-9, -18, 0, 25, 4);

        System.out.print("The maximum value is : ");

        // Using stream.max() to get maximum
        // element according to provided Comparator
        // and storing in variable var
        Integer var = list.stream().max(Integer::compare).get();

        System.out.print(var);
    }
}
```

输出:

```java
The maximum value is : 25

```

**例 2 :**

```java
// Implementation of Stream.max()
// to get the maximum element
// of the Stream according to the
// provided Comparator.
import java.util.*;
import java.util.Optional;
import java.util.Comparator;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = Arrays.asList(-9, -18, 0, 25, 4);

        // Using stream.max() to get maximum
        // element according to provided Comparator
        // Here, the smallest element in list
        // will be stored in variable var
        Optional<Integer> var = list.stream()
                     .max(Comparator.reverseOrder());

        // If a value is present, isPresent()
        // will return true, else display message
        if (var.isPresent()) {
            System.out.println(var.get());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

输出:

```java
-18

```

**例 3 :**

```java
// Implementation of Stream.max()
// to get the maximum element
// of the Stream according to the
// provided Comparator.
import java.util.*;
import java.util.Optional;
import java.util.Comparator;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("G", "E", "E", "K",
                                          "g", "e", "e", "k");

        // using Stream.max() method with Comparator
        // Here, the character with maximum ASCII value
        // is stored in variable MAX
        String MAX = list.stream().max(Comparator.
                       comparing(String::valueOf)).get();

        // Displaying the maximum element in
        // the stream according to provided Comparator
        System.out.println("Maximum element in the "
                           + "stream is : " + MAX);
    }
}
```

输出:

```java
Maximum element in the stream is : k

```

**例 4 :**

```java
// Implementation of Stream.max()
// to get the maximum element
// of the Stream according to the
// provided Comparator.
import java.util.*;
import java.util.Optional;
import java.util.Comparator;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating an array of strings
        String[] array = { "Geeks", "for", "GeeksforGeeks",
                           "GeeksQuiz" };

        // Here, the Comparator compares the strings
        // based on their last characters and returns
        // the maximum value accordingly
        // The result is stored in variable MAX
        Optional<String> MAX = Arrays.stream(array).max((str1, str2) ->  
                       Character.compare(str1.charAt(str1.length() - 1), 
                                       str2.charAt(str2.length() - 1)));

        // If a value is present,
        // isPresent() will return true
        if (MAX.isPresent()) 
            System.out.println(MAX.get());        
        else 
            System.out.println("-1");        
    }
}
```

输出:

```java
GeeksQuiz

```
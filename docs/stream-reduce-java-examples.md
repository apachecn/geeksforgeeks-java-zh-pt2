# Java 中的 Stream.reduce()示例

> 原文:[https://www.geeksforgeeks.org/stream-reduce-java-examples/](https://www.geeksforgeeks.org/stream-reduce-java-examples/)

很多时候，我们需要执行操作，其中一个流减少到单个结果值，例如，最大值、最小值、总和、乘积等。还原是组合所有元素的重复过程。

*reduce* 操作对流中的每个元素应用二元运算符，其中运算符的第一个参数是前一个应用程序的返回值，第二个参数是当前流元素。

**语法:**

```
T reduce(T identity, BinaryOperator<T> accumulator);

Where, identity is initial value 
of type T and accumulator is a 
function for combining two values.

```

sum()、min()、max()、count()等。是一些简化操作的例子。reduce()明确要求您指定如何减少流中的数据。

让我们看一些例子来更好地理解 reduce()函数:
**例 1 :**

```
// Implementation of reduce method
// to get the longest String
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a list of Strings
        List<String> words = Arrays.asList("GFG", "Geeks", "for",
                                           "GeeksQuiz", "GeeksforGeeks");

        // The lambda expression passed to
        // reduce() method takes two Strings
        // and returns the longer String.
        // The result of the reduce() method is
        // an Optional because the list on which
        // reduce() is called may be empty.
        Optional<String> longestString = words.stream()
                                   .reduce((word1, word2)
                             -> word1.length() > word2.length()
                                           ? word1 : word2);

        // Displaying the longest String
        longestString.ifPresent(System.out::println);
    }
}
```

输出:

```
GeeksforGeeks

```

**例 2 :**

```
// Implementation of reduce method
// to get the combined String
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // String array
        String[] array = { "Geeks", "for", "Geeks" };

        // The result of the reduce() method is
        // an Optional because the list on which
        // reduce() is called may be empty.
        Optional<String> String_combine = Arrays.stream(array)
                                           .reduce((str1, str2)
                                           -> str1 + "-" + str2);

        // Displaying the combined String
        if (String_combine.isPresent()) {
            System.out.println(String_combine.get());
        }
    }
}
```

输出:

```
Geeks-for-Geeks

```

**例 3 :**

```
// Implementation of reduce method
// to get the sum of all elements
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating list of integers
        List<Integer> array = Arrays.asList(-2, 0, 4, 6, 8);

        // Finding sum of all elements
        int sum = array.stream().reduce(0,
                (element1, element2) -> element1 + element2);

        // Displaying sum of all elements
        System.out.println("The sum of all elements is " + sum);
    }
}
```

输出:

```
The sum of all elements is 16

```

**例 4 :**

```
// Implementation of reduce method
// to get the product of all numbers
// in given range.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // To get the product of all elements
        // in given range excluding the
        // rightmost element
        int product = IntStream.range(2, 8)
                     .reduce((num1, num2) -> num1 * num2)
                     .orElse(-1);

        // Displaying the product
        System.out.println("The product is : " + product);
    }
}
```

输出:

```
The product is : 5040

```
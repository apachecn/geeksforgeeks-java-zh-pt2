# Java 中的流

> 原文:[https://www.geeksforgeeks.org/stream-in-java/](https://www.geeksforgeeks.org/stream-in-java/)

在 Java 8 中引入了流应用编程接口，用于处理对象集合。流是支持各种方法的对象序列，这些方法可以通过流水线来产生所需的结果。
Java 流的特点是–

*   流不是数据结构，而是从集合、数组或输入/输出通道获取输入。
*   流不改变原始的数据结构，它们只根据流水线方法提供结果。
*   每个中间操作都被延迟执行，并作为结果返回一个流，因此各种中间操作可以被流水线化。终端操作标记流的结尾并返回结果。

流上的不同操作-
**中间操作:**

1.  **map:**map 方法用于返回一个流，该流由给定函数应用于该流元素的结果组成。
    `List number = Arrays.asList(2,3,4,5);
    List square = number.stream().map(x->x*x).collect(Collectors.toList());`
2.  **筛选:**筛选方法用于根据作为参数传递的谓词选择元素。
    `List names = Arrays.asList("Reflection","Collection","Stream");
    List result = names.stream().filter(s->s.startsWith("S")).collect(Collectors.toList());`
3.  **排序:**排序方法用于对流进行排序。
    `List names = Arrays.asList("Reflection","Collection","Stream");
    List result = names.stream().sorted().collect(Collectors.toList());`

**终端操作:**

1.  **收集:**收集方法用于返回对流执行的中间操作的结果。
    `List number = Arrays.asList(2,3,4,5,3);
    Set square = number.stream().map(x->x*x).collect(Collectors.toSet());`
2.  **forEach:**forEach 方法用于迭代流的每个元素。
    `List number = Arrays.asList(2,3,4,5);
    number.stream().map(x->x*x).forEach(y->System.out.println(y));`
3.  **reduce:**reduce 方法用于将流的元素减少到单个值。
    reduce 方法以 BinaryOperator 为参数。

`List number = Arrays.asList(2,3,4,5);
int even = number.stream().filter(x->x%2==0).reduce(0,(ans,i)-> ans+i);`

这里一个变量被赋值为 0 作为初始值，I 被加入其中。

**演示流使用的程序**

```
//a simple program to demonstrate the use of stream in java
import java.util.*;
import java.util.stream.*;

class Demo
{
  public static void main(String args[])
  {

    // create a list of integers
    List<Integer> number = Arrays.asList(2,3,4,5);

    // demonstration of map method
    List<Integer> square = number.stream().map(x -> x*x).
                           collect(Collectors.toList());
    System.out.println(square);

    // create a list of String
    List<String> names =
                Arrays.asList("Reflection","Collection","Stream");

    // demonstration of filter method
    List<String> result = names.stream().filter(s->s.startsWith("S")).
                          collect(Collectors.toList());
    System.out.println(result);

    // demonstration of sorted method
    List<String> show =
            names.stream().sorted().collect(Collectors.toList());
    System.out.println(show);

    // create a list of integers
    List<Integer> numbers = Arrays.asList(2,3,4,5,2);

    // collect method returns a set
    Set<Integer> squareSet =
         numbers.stream().map(x->x*x).collect(Collectors.toSet());
    System.out.println(squareSet);

    // demonstration of forEach method
    number.stream().map(x->x*x).forEach(y->System.out.println(y));

    // demonstration of reduce method
    int even =
       number.stream().filter(x->x%2==0).reduce(0,(ans,i)-> ans+i);

    System.out.println(even);
  }
}
```

输出:

```
[4, 9, 16, 25]
[Stream]
[Collection, Reflection, Stream]
[16, 4, 9, 25]
4
9
16
25
6

```

**重要点/观察:**

1.  一个流由源和一个终端方法组成，源后面跟零个或多个中间方法，中间方法组合在一起(流水线式)，终端方法按照描述的方法处理从源获得的对象。
2.  流用于根据流水线方法计算元素，而不改变对象的原始值。

本文由**阿卡什·奥哈**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
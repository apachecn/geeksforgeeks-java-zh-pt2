# Java 8 中数组上的流

> 原文:[https://www.geeksforgeeks.org/streams-arrays-java-8/](https://www.geeksforgeeks.org/streams-arrays-java-8/)

在本文中，我们将介绍在 Java 8 中添加的数组类的流方法，它简化了对数组的许多操作，并且提高了效率。
java 8 中添加了不同的特性，如 lambdas 和 streams，使得 Java 能够高效地编写优雅的代码，这些代码提高了可读性，在大多数情况下提高了性能效率。

**语法:**

```
public static IntStream stream(int[] arr)
Parameter :
arr - An array which is to be converted to the stream
Returns :
An IntStream of an array
```

变化:

```
public static IntStream stream(int[] array)
public static IntStream stream(int[] array, int startInclusive, int endExclusive)
public static DoubleStream stream(double[] array)
public static DoubleStream stream(double[] array, int startInclusive, int endExclusive)
public static LongStream stream(long[] array)
public static LongStream stream(long[] array, int startInclusive, int endExclusive)
public static  Stream stream(T[] array)
public static  Stream stream(T[] array, int startInclusive, int endExclusive)
```

**先决条件:-**

*   [Java 8 中的 Lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)
*   [Java 中的流](https://www.geeksforgeeks.org/stream-in-java/)

**注意:**–即使您不熟悉这些主题，也可以通读这篇文章，因为它使用了非常基本的 lambda 表达式，并解释了如何使用 stream 类的方法。

让我们看一个阵列上的流示例。在这个例子中，我们将找到数组元素的平均值，并将看到以命令式和声明式方式编写代码的不同之处

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Arrays;
class GFG_Demo_1 {
    public static void main(String[] args)
    {
        int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10,
            11, 12, 13, 14, 15, 16, 17, 18, 19, 20 };

        // Let's try the imperative style first(which we
        // are familiar with)
        int sum = 0;
        for (int i = 0; i < arr.length; i++)
            sum += arr[i];
        System.out.println("Average using iteration :" +
                                    (sum / arr.length));

        // Let's try the declarative style now
        sum = Arrays.stream(arr) // Step 1
                  .sum(); // Step 2
        System.out.println("Average using streams : " +
                                   (sum / arr.length));

        // forEach()
        // It iterates through the entire streams
        System.out.println("Printing array elements : ");
        Arrays.stream(arr)
            .forEach(e->System.out.print(e + " "));
    }
}
```

**输出:**

```
Average using iteration :10
Average using streams : 10
Printing array elements :
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
```

在上面的例子中，您已经看到了流工作，让我们看看这些步骤是做什么的。

**第 1 步:**
Arrays . stream(arr)–在这一步我们调用 Arrays 类上的 stream 方法，将 arr 作为参数传递给这个语句返回的函数 [IntStream](https://docs.oracle.com/javase/8/docs/api/java/util/stream/IntStream.html) 。

**第二步:**
array . stream(arr)。sum()–一旦我们获得了 IntStream，我们就可以使用 IntStream 接口的不同方法。
当你通过[进入](https://docs.oracle.com/javase/8/docs/api/java/util/stream/IntStream.html)时。接口文档您可以打开每个方法来查看它是执行终端操作还是中间操作。我们应该相应地在终端或中间使用这种方法。
现在我们来看看 IntStream 的不同方法，看看这些方法执行什么操作。我们将看到所有这些方法与数组对比的例子..

在下面的例子中，我们将通过以下方法。

1.  asDoubleStream()
2.  asLongStream()
3.  任何匹配()
4.  所有匹配（）
5.  noneMatch()

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Arrays;
import java.util.function.IntPredicate;
class GFG_Demo_2 {
  public static void main(String[] args)
  {
        int arr_sample1[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10,
                 11, 12, 13, 14, 15, 16, 17, 18, 19, 20 };

        // asDoubleStream()
        // It converts the original array to double
        System.out.println("Example of asDoubleStream(): ");
        Arrays.stream(arr_sample1)
            .asDoubleStream()
            .forEach(e->System.out.print(e + " "));

        // asLongStream()
        // It converts the original array to Long
        System.out.println("\nExample of asLongStream");
        Arrays.stream(arr_sample1)
            .asLongStream()
            .forEach(e->System.out.print(e + " "));

        int arr_sample2[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9,
            10, 23, 12, 13, 14, 15, 16, 17, 18, 19, 20 };

        // anyMatch()
        // This method find whether the given predicate
        // is in the array or not
        System.out.println("\nExample of anyMatch");

        // Test whether any of the element in array is
        // divisible by 11 or not
        IntPredicate predicate = e->e % 11 == 0;
        System.out.println(Arrays.stream(arr_sample2)
                               .anyMatch(predicate));

        // You can directly write the lambda expression
        // which computes to IntPredicate
        // Uncomment to test
        // System.out.println(Arrays.stream(arr)
        // .anyMatch(e -> e % 11 == 0));

        int arr_sample3[] = { 2, 4, 6, 8, 10 };
        int arr_sample4[] = { 1, 3, 5, 7, 11 };

        // allMatch()
        // This method finds whether the given predicate
        // matches the entire array or not
        System.out.println("Example of allMatch :");

        // Returns true as all the elements of arr_sample3
        // is even
        System.out.println(Arrays.stream(arr_sample3)
                               .allMatch(e->e % 2 == 0));

        // Returns false as all the elements of arr_sammple4
        // is odd
        System.out.println(Arrays.stream(arr_sample4)
                               .allMatch(e->e % 2 == 0));

        // noneMatch()
        System.out.println("Example of noneMatch");
        System.out.println(Arrays.stream(arr_sample4)
                               .noneMatch(e->e % 2 == 0));
    }
}
```

**输出:**

```
Example of asDoubleStream():
1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0 11.0 12.0 13.0
14.0 15.0 16.0 17.0 18.0 19.0 20.0
Example of asLongStream
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
Example of anyMatch
false
Example of allMatch :
true
false
Example of noneMatch
true
```

我们看到的方法很少，尽管 IntStream 提供了更多的方法，让我们尝试更多的方法。
我们将在下面的例子中经历以下方法。

1.  平均值()
2.  手机（）
3.  findFirst()
4.  最大值()
5.  最小值()
6.  减少()

请记住，所有这些方法都返回[选项线](https://docs.oracle.com/javase/8/docs/api/java/util/OptionalInt.html)或[选项线](https://docs.oracle.com/javase/8/docs/api/java/util/OptionalDouble.html)，而不是整数或双精度。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Arrays;
class GFG_Demo_3 {
    public static void main(String[] args)
    {
        int arr_sample1[] = { 11, 2, 3, 42, 5, 6, 17, 8, 9,
               10, 11, 12, 13, 24, 55, 16, 47, 18, 19, 20 };
        System.out.println("These method returns Optional");

        // average()
        // This method returns a average of an array
        System.out.println("Example of average() : ");
        System.out.println((Arrays.stream(arr_sample1)
                                .average()));

        // findAny()
        // It can return any value from the stream
        // Most of the time it returns the first value
        // but it is not assured it can return any value
        System.out.println("Example of findAny() : ");
        System.out.println(Arrays.stream(arr_sample1)
                               .findAny());

        // findFirst()
        // It returns the first element of the stream
        System.out.println("Example of findFirst() :");
        System.out.println(Arrays.stream(arr_sample1)
                               .findFirst());

        // max()
        // It returns the max element in an array
        System.out.println("Example of max() :");
        System.out.println(Arrays.stream(arr_sample1)
                               .max());

        // min()
        // It returns the max element in an array
        System.out.println("Example of max() :");
        System.out.println(Arrays.stream(arr_sample1)
                               .min());

        // reduce()
        // It reduces the array by certain operation
        // Here it performs addition of array elements
        System.out.println("Example of reduce() :");
        System.out.println(Arrays.stream(arr_sample1)
                               .reduce((x, y)->x + y));

        // reduce() have another variation which we will
        // see in different example
    }
}
```

**Output**

```
These method returns Optional
Example of average() : 
OptionalDouble[17.4]
Example of findAny() : 
OptionalInt[11]
Example of findFirst() :
OptionalInt[11]
Example of max() :
OptionalInt[55]
Example of max() :
OptionalInt[2]
Example of reduce() :
OptionalInt[348]
```

但是使用这个 OptionalInt 和 OptionalDouble 变得非常困难，因此 Java 提供了将它们转换成 Double 和 Int 值的方法，这样就可以很容易地重用它们

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Arrays;
class GFG_Demo_4 {
public static void main(String[] args)
    {
        int arr_sample1[] = { 11, 2, 3, 42, 5, 6, 17, 8, 9,
                10, 11, 12, 13, 24, 55, 16, 47, 18, 19, 20 };
        System.out.println("These method convert Optional to primitive");

        // OptionalDouble can be converted to double by using getAsDouble()
        // if average doesn't contains any value it throws NoSuchElementException
        System.out.println("Example of average() : ");
        System.out.println((Arrays.stream(arr_sample1)
                                .average()
                                .getAsDouble()));

        // OptionalInt can be converted to int by using getAsInt()
        System.out.println("Example of findAny() : ");
        System.out.println(Arrays.stream(arr_sample1)
                               .findAny()
                               .getAsInt());
    }
}
```

**输出:**

```
These method convert Optional to primitive
Example of average() :
17.4
Example of findAny() :
11
```

IntStream 提供了更多的方法，我们将在不同的文章中介绍，并且将使用不同的流方法。

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/arrays . html](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html)
[https://docs . Oracle . com/javase/8/docs/API/Java/util/stream/intstream . html](https://docs.oracle.com/javase/8/docs/api/java/util/stream/IntStream.html)

本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
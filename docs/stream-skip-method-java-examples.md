# Java 中的 Stream skip()方法，带示例

> 原文:[https://www . geesforgeks . org/stream-skip-method-Java-examples/](https://www.geeksforgeeks.org/stream-skip-method-java-examples/)

**先决条件:**[Java 中的 Streams](https://www.geeksforgeeks.org/stream-in-java/)
这个 skip(长 N)是 **java.util.stream.Stream** 对象的一个方法。此方法以一个长(N)作为参数，并在移除前 N 个元素后返回一个流。如果 N 的值很大，skip()在有序并行流水线上可能相当昂贵，因为 skip(N)被约束为跳过相遇顺序中的前 N 个元素，而不仅仅是任何 N 个元素。
**注意:**如果一个流包含的元素少于 N 个，则返回一个空流。

**语法:**

```java
Stream<T> skip(long N)

Where N is the number of elements to be skipped
and this function returns new stream as output.

```

**异常:**如果 N 的值为负，则函数抛出 **IllegalArgumentException** 。

**例 1 :** 跳跃功能的实现。

```java
// Java code for skip() function
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = new ArrayList<Integer>();

        // adding elements in the list
        list.add(-2);
        list.add(0);
        list.add(2);
        list.add(4);
        list.add(6);
        list.add(8);
        list.add(10);
        list.add(12);
        list.add(14);
        list.add(16);

        // setting the value of N as 4
        int limit = 4;
        int count = 0;
        Iterator<Integer> it = list.iterator();

        // Iterating through the list of integers
        while (it.hasNext()) {
            it.next();
            count++;

            // Check if first four i.e, (equal to N)
            // integers are iterated.
            if (count <= limit) {

                // If yes then remove first N elements.
                it.remove();
            }
        }

        System.out.print("New stream is : ");

        // Displaying new stream
        for (Integer number : list) {
            System.out.print(number + " ");
        }
    }
}
```

输出:

```java
New stream is : 6 8 10 12 14 16 

```

**应用:**

```java
// Java code for skip() function
import java.util.stream.Stream;
import java.util.ArrayList;
import java.util.List;
 class gfg{

     // Function to skip the elements of stream upto given range, i.e, 3
     public static Stream<String> skip_func(Stream<String> ss, int range){
         return ss.skip(range);
     }

     // Driver code
     public static void main(String[] args){

         // list to save stream of strings
         List<String> arr = new ArrayList<>();

         arr.add("geeks");
         arr.add("for");
         arr.add("geeks");
         arr.add("computer");
         arr.add("science");

         Stream<String> str = arr.stream();

         // calling function to skip the elements to range 3
         Stream<String> sk = skip_func(str,3);
         sk.forEach(System.out::println);
     }
 }
```

输出:

```java
computer
science

```

**限制()和跳过()的区别:**

1.  limit()方法返回前 N 个元素的精简流，而 skip()方法在跳过前 N 个元素后返回剩余元素的流。
2.  limit()是一个短路的有状态中间操作，即当用无限输入处理时，它可能会产生一个有限的流，而不会处理整个输入，但是 skip()是一个有状态中间操作，即它可能需要在产生结果之前处理整个输入。
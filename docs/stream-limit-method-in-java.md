# Java 中的 stream.limit()方法

> 原文:[https://www.geeksforgeeks.org/stream-limit-method-in-java/](https://www.geeksforgeeks.org/stream-limit-method-in-java/)

**先决条件:**[Java8 中的流](https://www.geeksforgeeks.org/stream-in-java/)
**限制(长 N)** 是 **java.util.stream.Stream** 对象的一种方法。此方法以一个(长 N)作为参数，并返回大小不超过 N 的流。如果 N 的值很大，limit()在有序并行管道上可能相当昂贵，因为 limit(N)被约束为返回相遇顺序中的前 N 个元素，而不仅仅是任何 N 个元素。

**语法:**

```
Stream<T> limit(long N)

Where N is the number of elements the stream should be 
limited to and this function returns new stream as output.

```

**异常:**如果 N 的值为负，则函数抛出 **IllegalArgumentException** 。

下面是一些例子，可以更好地理解函数的实现。
**例 1 :**

```
// Java code to show implementation
// of limit() function
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
            if (count > limit) {

                // If yes then remove all the remaining integers.
                it.remove();
            }
        }

        System.out.print("New stream of length N"
                         + " after truncation is : ");

        // Displaying new stream of length
        // N after truncation
        for (Integer number : list) {
            System.out.print(number + " ");
        }
    }
}
```

输出:

```
New stream of length N after truncation is : -2 0 2 4 

```

**应用:**

```
// Java code to show the use of limit() function
import java.util.stream.Stream;
import java.util.ArrayList;
import java.util.List;
 class gfg{

     // Function to limit the stream upto given range, i.e, 3
     public static Stream<String> limiting_func(Stream<String> ss, int range){
         return ss.limit(range);
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

         // calling function to limit the stream to range 3
         Stream<String> lm = limiting_func(str,3);
         lm.forEach(System.out::println);
     }
 }
```

输出:

```
geeks
for
geeks

```
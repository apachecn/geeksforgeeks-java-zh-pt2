# Java 中带流过滤器的列表总和

> 原文:[https://www.geeksforgeeks.org/sum-list-stream-filter-java/](https://www.geeksforgeeks.org/sum-list-stream-filter-java/)

当在一个范围内添加整数时，我们通常会遍历列表，但是 **java.util.stream.Stream** 有一个 **sum()** 方法，当与 **filter()** 一起使用时，很容易给出所需的结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Simple method (without filter) to find sum of a list
import java.util.*;

class Addition {
    public static void main(String[] args)
    {
        // create a list of integers
        List<Integer> list = new ArrayList<Integer>();

        // add elements to the list
        list.add(1);
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(8);
        list.add(9);
        list.add(10);

        System.out.println(sum(list));
    }

    public static int sum(List<Integer> list)
    {
        // iterator for accessing the elements
        Iterator<Integer> it = list.iterator();

        int res = 0;
        while (it.hasNext()) {
            int num = it.next();

            // adding the elements greater than 5
            if (num > 5) {
                res += num;
            }
        }

        return res;
    }
}
```

**Output:** 

```java
40
```

使用 **sum()** 方法和 [**filter()**](https://www.geeksforgeeks.org/stream-filter-java-examples/) 方法
可以轻松执行上述任务

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Using stream filter to find sum of a list
import java.util.*;

class Addition {
    public static void main(String[] args)
    {
        // create a list of integers
        List<Integer> list = new ArrayList<Integer>();

        // add elements to the list
        list.add(1);
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(8);
        list.add(9);
        list.add(10);

        System.out.println(sum(list));
    }

    public static int sum(List<Integer> list)
    {
        // create a stream of integers
        // filter the stream
        // add the integers
        return list.stream()
            .filter(i -> i > 5)
            .mapToInt(i -> i)
            .sum();
    }
}
```

**Output:** 

```java
40
```
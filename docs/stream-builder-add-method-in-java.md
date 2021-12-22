# 小溪。Java 中的 Builder add()方法

> 原文:[https://www . geesforgeks . org/stream-builder-add-method-in-Java/](https://www.geeksforgeeks.org/stream-builder-add-method-in-java/)

**小溪。Builder add(T t)** 用于在流的构建阶段将元素插入到元素中。它向正在构建的流中添加一个元素。

**语法:**

```
default Stream.Builder<T> add(T t)
```

**参数:**此方法添加一个强制参数 **t** ，它是要输入到流中的元素。

**异常:**当构建器已经转换到构建状态时，该方法抛出**illegalstatexception:**。这意味着该流已经进入构建阶段，现在不能更改。因此，没有更多的元素可以添加到流中。

以下是说明 add()方法的示例:

**例 1:**

```
// Java code to show the implementation
// of Stream.Builder add(T t)

import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        Stream.Builder<String> str_b = Stream.builder();

        // Inserting elements into the stream
        // using Stream.Builder add(T t)
        str_b.add("Geeks");
        str_b.add("for");
        str_b.add("GeeksforGeeks");
        str_b.add("Data Structures");
        str_b.add("Geeks Classes");

        // Creating the String Stream
        // The stream has now entered the built phase
        Stream<String> s = str_b.build();

        // printing the elements
        System.out.println("Stream successfully built");
        s.forEach(System.out::println);
    }
}
```

**Output:**

```
Stream successfully built
Geeks
for
GeeksforGeeks
Data Structures
Geeks Classes

```

**示例 2:** 说明 IllegalStateException

```
// Java code to show the implementation
// of Stream.Builder add(T t)

import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        Stream.Builder<String> str_b = Stream.builder();

        // using Stream.Builder add(T t)
        str_b.add("5");
        str_b.add("6");
        str_b.add("7");
        str_b.add("8");
        str_b.add("9");

        // Creating the String Stream
        // The stream has now entered the built phase
        Stream<String> s = str_b.build();

        // printing the elements
        System.out.println("Stream successfully built");
        s.forEach(System.out::println);

        // Trying to add another element into the stream
        // Since the Stream is in built phase
        // This operation is not possible now
        // Hence add() will throw exception now

        try {
            str_b.add("50");
        }
        catch (Exception e) {
            System.out.println("Exception thrown "
                               + "when now adding element into the stream: "
                               + e);
        }
    }
}
```

**Output:**

```
Stream successfully built
5
6
7
8
9
Exception thrown when now adding element into the stream: java.lang.IllegalStateException

```
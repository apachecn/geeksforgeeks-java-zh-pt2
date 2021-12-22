# 小溪。Java 中的 Builder accept()方法

> 原文:[https://www . geesforgeks . org/stream-builder-accept-method-in-Java/](https://www.geeksforgeeks.org/stream-builder-accept-method-in-java/)

**小溪。Builder accept(T t)** 用于在流的构建阶段将元素插入到元素中。它向正在构建的流中添加一个元素。

**语法:**

```java
void accept(T t)
```

**参数:**该方法接受一个强制参数 **t** ，它是输入到流中的元素。

**异常:**当构建器已经转换到构建状态时，该方法抛出**illegalstatexception:**。这意味着该流已经进入构建阶段，现在不能更改。因此，没有更多的元素可以添加到流中。

下面是举例说明 accept()方法的例子:

**例 1:**

```java
// Java code to show the implementation
// of Stream.Builder accept(T t)

import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        Stream.Builder<String> str_b = Stream.builder();

        // Inserting elements into the stream
        // using Stream.Builder accept(T t)
        str_b.accept("Geeks");
        str_b.accept("for");
        str_b.accept("GeeksforGeeks");
        str_b.accept("Data Structures");
        str_b.accept("Geeks Classes");

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

```java
Stream successfully built
Geeks
for
GeeksforGeeks
Data Structures
Geeks Classes

```

**示例 2:** 说明 IllegalStateException

```java
// Java code to show the implementation
// of Stream.Builder accept(T t)

import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        Stream.Builder<String> str_b = Stream.builder();

        // using Stream.Builder accept(T t)
        str_b.accept("5");
        str_b.accept("6");
        str_b.accept("7");
        str_b.accept("8");
        str_b.accept("9");

        // Creating the String Stream
        // The stream has now entered the built phase
        Stream<String> s = str_b.build();

        // printing the elements
        System.out.println("Stream successfully built");
        s.forEach(System.out::println);

        // Trying to add another element into the stream
        // Since the Stream is in built phase
        // This operation is not possible now
        // Hence accept() will throw exception now

        try {
            str_b.accept("50");
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

```java
Stream successfully built
5
6
7
8
9
Exception thrown when now adding element into the stream: java.lang.IllegalStateException

```
# 小溪。Java 中的 Builder build()

> 原文:[https://www.geeksforgeeks.org/stream-builder-build-in-java/](https://www.geeksforgeeks.org/stream-builder-build-in-java/)

小溪。Builder build()构建流，将此构建器转换为已构建状态。

**语法:**

```java
Stream<**T**> build()

```

**异常:**

*   **illegalstatexception:**如果构建器已经过渡到构建状态，则抛出**illegalstatexception**。它表示某个方法在非法或不适当的时间被调用。换句话说，对于所请求的操作，Java 环境或 Java 应用程序不处于合适的状态。

**返回值:**已建流。

**注意:**流构建器有一个生命周期，从构建阶段开始，在此期间可以添加元素，然后过渡到构建阶段，之后可以不添加元素。构建阶段在调用 build()方法时开始，该方法创建一个有序流，其元素是按照添加顺序添加到流构建器中的元素。

**例 1 :**

```java
// Java code to show the implementation
// of Stream.Builder build()
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        Stream.Builder<String> str_b = Stream.builder();

        str_b.add("Geeks");
        str_b.add("for");
        str_b.add("GeeksforGeeks");
        str_b.add("Data Structures");
        str_b.add("Geeks Classes");

        // creating the string stream
        Stream<String> s = str_b.build();

        // printing the elements
        s.forEach(System.out::println);
    }
}
```

输出:

```java
Geeks
for
GeeksforGeeks
Data Structures
Geeks Classes

```

**例 1 :**

```java
// Java code to show the implementation
// of Stream.Builder build()
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        Stream.Builder<String> str_b = Stream.builder();

        str_b.add("Geeks");
        str_b.add("for");
        str_b.add("GeeksforGeeks");
        str_b.add("Data Structures");
        str_b.add("Geeks Classes");

        // creating the string stream
        Stream<String> s = str_b.build();

        // printing the elements
        s.forEach(System.out::println);
    }
}
```

输出:

```java
Geeks
for
GeeksforGeeks
Data Structures
Geeks Classes

```
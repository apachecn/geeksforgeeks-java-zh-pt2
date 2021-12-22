# Java 中()方法的流

> 原文:[https://www.geeksforgeeks.org/stream-of-method-in-java/](https://www.geeksforgeeks.org/stream-of-method-in-java/)

### **T(T)流**

**(T ^ T)**流返回包含单个元素的顺序流。
**语法:**

```
static Stream of(T t)

```

**参数:**该方法接受一个强制参数 **t** ，它是流中的单个元素。

**返回值:**的流返回一个包含**单个**指定元素的连续流。

**示例:**

```
// Java code for Stream of(T t)
// to get a sequential Stream
// containing a single element.

import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an Stream having single element only
        Stream stream = Stream.of("Geeks");

        // Displaying the Stream having single element
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```
Geeks

```

### **流量(T…值)**

**流(T…值)**返回一个顺序的有序流，其元素是指定的值。

**语法:**

```
static Stream of(T... values)

```

**参数:**该方法接受强制参数**值**，这是新流的元素。

**返回值:**流(T…值)返回一个顺序的有序流，其元素是指定的值。

**示例:**

```
// Java code for Stream of(T... values)
// to get a sequential ordered stream whose
// elements are the specified values.

import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an Stream
        Stream stream = Stream.of("Geeks", "for", "Geeks");

        // Displaying the sequential ordered stream
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```
Geeks
for
Geeks

```
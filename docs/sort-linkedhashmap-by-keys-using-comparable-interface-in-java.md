# 使用 Java 中的可比接口按键对链接的哈希表进行排序

> 原文:[https://www . geeksforgeeks . org/sort-link edhashmap-by-key-use-compatible-in-interface-in-Java/](https://www.geeksforgeeks.org/sort-linkedhashmap-by-keys-using-comparable-interface-in-java/)

[链接散列表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)就像[散列表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)一样，有一个额外的特性，保持插入其中的元素的顺序。HashMap 从不维护 LinkedHashMap 提供的插入轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。

为了首先使用 Java 中的[可比](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)接口按键对 LinkedHashMap 进行排序，我们创建了一个实现可比接口的类。在这个类中，我们覆盖了 [compareTo()](https://www.geeksforgeeks.org/boolean-compareto-method-in-java-with-examples/) 方法。

```
// Student class implements comparable interface

class Student implements Comparable<Student> {
    String name;

    Student(String name) {
        this.name = name;
    }

    // Override toString method
    public String toString() {
        return this.name;
    }

    // Override compareTo method
    public int compareTo(Student stu) {
        return this.name.compareTo(stu.name);
    }
}
```

然后我们将 LinkedHashMap 传递给 TreeMap 构造函数进行排序。

```
TreeMap<Student, Integer> tree_map = new TreeMap<>(map);
```

以下是该方法的全面实施:

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate how to Sort LinkedHashMap by
// keys using Comparable interface
import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {
    String name;

    Student(String name) { this.name = name; }

    // override toString method
    public String toString() { return this.name; }

    // Override compareTo method to sort LinkedHashMap keys
    // in ascending order
    public int compareTo(Student stu)
    {
        return this.name.compareTo(stu.name);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New LinkedHashMap
        LinkedHashMap<Student, Integer> map
            = new LinkedHashMap<>();

        // Adding elements to the map
        map.put(new Student("Bina"), 200);
        map.put(new Student("Akshay"), 400);
        map.put(new Student("Chintu"), 500);

        // Print Before sort
        System.out.println(
            "Before sort keys in ascending order : " + map);

        // TreeMap to sort LinkedHashMap using comparable
        TreeMap<Student, Integer> tree_map
            = new TreeMap<>(map);

        // Print after sorting
        System.out.println(
            "After sort keys in ascending order : "
            + tree_map);
    }
}
```

**Output**

```
Before sort keys in ascending order : {Bina=200, Akshay=400, Chintu=500}
After sort keys in ascending order : {Akshay=400, Bina=200, Chintu=500}
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate how to Sort LinkedHashMap by
// keys using Comparable interface
import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {
    String name;

    Student(String name) { this.name = name; }

    // override toString method
    public String toString() { return this.name; }

    // Override compareTo method to sort LinkedHashMap keys
    // in descending order
    public int compareTo(Student stu)
    {
        return stu.name.compareTo(this.name);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New LinkedHashMap
        LinkedHashMap<Student, Integer> map
            = new LinkedHashMap<>();

        // Adding elements to the map
        map.put(new Student("Bina"), 200);
        map.put(new Student("Akshay"), 400);
        map.put(new Student("Chintu"), 500);

        // Print Before sort
        System.out.println(
            "Before sort keys in descending order : " + map);

        // TreeMap to sort LinkedHashMap using comparable
        TreeMap<Student, Integer> tree_map
            = new TreeMap<>(map);

        // Print after sorting
        System.out.println(
            "After sort keys in descending order : "
            + tree_map);
    }
}
```

**Output**

```
Before sort keys in descending order : {Bina=200, Akshay=400, Chintu=500}
After sort keys in descending order : {Chintu=500, Bina=200, Akshay=400}
```
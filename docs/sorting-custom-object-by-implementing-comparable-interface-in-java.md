# 通过在 Java 中实现可比接口对自定义对象进行排序

> 原文:[https://www . geesforgeks . org/sorting-custom-object-by-implementing-compatible-in-interface-Java/](https://www.geeksforgeeks.org/sorting-custom-object-by-implementing-comparable-interface-in-java/)

Java 提供了两个使用类的数据成员对对象进行排序的接口，它们是**可比的**和[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)。在本文中，我们将关注一个可比较的界面。一个可比较的对象能够通过自然排序将自己与另一个对象进行比较。该类必须实现 Java . lang . compatible 接口来比较其实例。

使用可比界面，我们可以分类:

*   字符串对象
*   包装类对象
*   用户定义的对象

**语法**

```java
public interface Comparable<T> 
{
    public int compareTo(T o);
}
```

其中 **T** 是要排序的对象类型。

**compareTo()方法**

对于任何支持排序的类，它都应该实现 Comparable 接口并重写它的 compareTo()方法。如果对象小于指定对象，则返回负整数；如果对象相等，则返回零；如果对象大于指定对象，则返回正整数。

**例 1:** 根据学生成绩对给定数据进行排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to sort student
// data according to their marks

import java.util.*;

// implementing comparable interface
class StudentData implements Comparable<StudentData> {

    String name;
    int marks;

    // Constructor
    StudentData(String name, int marks)
    {
        this.name = name;
        this.marks = marks;
    }

    // overriding method to sort
    // the student data
    public int compareTo(StudentData sd)
    {
        return this.marks - sd.marks;
    }
}

// Driver class
class GFG {
    public static void main(String[] args)
    {

        ArrayList<StudentData> list
            = new ArrayList<StudentData>();

        // Inserting data
        list.add(new StudentData("Ram", 98));
        list.add(new StudentData("Shyam", 84));
        list.add(new StudentData("Lokesh", 90));

        Collections.sort(list);

        // Displaying data
        for (StudentData sd : list)
            System.out.println(sd.name + " " + sd.marks);
    }
}
```

**Output**

```java
Shyam 84
Lokesh 90
Ram 98
```

**例 2:** 根据名称对给定数据进行排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to sort student
// data according to their names

import java.util.*;

// implementing comparable interface
class StudentData implements Comparable<StudentData> {

    int roll;
    String name;
    int marks;

    // Constructor
    StudentData(int roll, String name, int marks)
    {
        this.roll = roll;
        this.name = name;
        this.marks = marks;
    }

    // overriding method to sort
    // the student data
    public int compareTo(StudentData sd)
    {

        // compareTo is a string method
        return this.name.compareTo(sd.name);
    }
}

// Driver class
class GFG {
    public static void main(String[] args)
    {

        ArrayList<StudentData> list
            = new ArrayList<StudentData>();

        // Inserting data
        list.add(new StudentData(1, "Ram", 98));
        list.add(new StudentData(2, "Shyam", 84));
        list.add(new StudentData(3, "Lokesh", 90));

        Collections.sort(list);

        // Displaying data
        for (StudentData sd : list)
            System.out.println(sd.roll + " " + sd.name + " "
                               + sd.marks);
    }
}
```

**Output**

```java
3 Lokesh 90
1 Ram 98
2 Shyam 84
```
# 对已经在 Java 中实现了可比的数组和包装类的元素进行排序

> 原文:[https://www . geeksforgeeks . org/排序-数组元素和包装类-已经在 java 中实现了可比较的/](https://www.geeksforgeeks.org/sorting-elements-of-arrays-and-wrapper-classes-that-already-implements-comparable-in-java/)

Java 提供了可比较的接口，可以使用类的数据成员对对象进行排序。可比界面只包含一个方法 [*【比较】(*](https://www.geeksforgeeks.org/java-lang-string-compareto/) )来比较两个对象，以在它们之间强加一个顺序。它返回一个负整数、零或正整数，以指示输入对象是否小于、等于 [*、*](https://www.geeksforgeeks.org/java-lang-string-compareto/) 或大于当前对象。它主要用于对自定义对象的数组或列表进行排序。

由于所有的[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)都已经实现了 Java Comparable 接口，所以它提供了 *compareTo()* 的默认实现，这就是为什么[T5】collections . sort()T7】和](https://www.geeksforgeeks.org/collections-sort-java-examples/)[T9】arrays . sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)函数可以在这些对象上使用的原因。将包含包装类的数组和列表的元素排序为已经实现可比接口的对象。

**插图:**

```
Input  :  {8 , 9 , 1 , 5 , 3 , 0}
Output :  {0 , 1 , 3 , 5 , 8 , 9}

Input  :  {"Ankit", "Parul" , "Swati" , "Tarun", "Akshat"}
Output :  {"Akshat" , "Ankit" , "Parul" , "Swati" , "Tarun"}
```

**实施:**

**示例**

## Java

```
// Java Program to Sorting Elements illustrating
// Array.srt) and Collection.sort() method
// Naive approach

// Importing all classes of
// java.util package
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Case 1: Array of Integer using sort()

        // Sorting array of integers
        // using Arrays.sort()
        // Custom input entries
        int[] a = { 8, 9, 1, 5, 3, 0 };

        // Print the array before sorting
        System.out.println("Before Sorting: "
                           + Arrays.toString(a));

        // By default sorting is in ascending order
        Arrays.sort(a);

        // Print the array after sorting
        System.out.println("After Sorting: "
                           + Arrays.toString(a));

        // Case 2: Array of string using sort()

        // Sorting array of Strings
        // using Arrays.sort()
        String[] str = { "Ankit", "Parul", "Swati", "Tarun",
                         "Akshat" };

        // Print the input array of string before sorting
        System.out.println("Before Sorting: "
                           + Arrays.toString(str));

        // Sort() method
        Arrays.sort(str);

        // Print the input array of string before sorting
        System.out.println("After Sorting: "
                           + Arrays.toString(str));

        // Case 3: Collectios.sort

        // Sorting List of String Collections.sort()

        // Creating an list object of string type
        // Custominput elements in object
        List<String> lt = Arrays.asList("Red", "Blue",
                                        "Green", "Black");

        // Print the elements before sorting
        System.out.println("Before Sorting:  " + lt);

        Collections.sort(lt);

        // Print the elements after sorting
        System.out.println("After Sorting:: " + lt);
    }
}
```

**输出**

```
Before Sorting: [8, 9, 1, 5, 3, 0]
After Sorting: [0, 1, 3, 5, 8, 9]
Before Sorting: [Ankit, Parul, Swati, Tarun, Akshat]
After Sorting: [Akshat, Ankit, Parul, Swati, Tarun]
Before Sorting:  [Red, Blue, Green, Black]
After Sorting:: [Black, Blue, Green, Red]
```

现在，如果我们想将一个用户定义的类排序成某种特定的顺序，那么我们必须实现存在于 *java.lang* 包中的 Comparable 接口，并提供*comparto(*)方法的实现。如果指定的为空或者如果指定对象的类型阻止它与对象进行比较，compareTo 方法还会抛出一个[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)或 [ClassCastException](https://www.geeksforgeeks.org/how-to-fix-java-lang-classcastexception-in-treeset/) 。

**实施:**

**示例**

## Java

```
// Java Program to Sorting Elements of Arrays and Wrapper
// Classes that Already Implements Comparable

// Importing all classes from
// java.util package
import java.util.*;

// Class 1
// Helper class
class Student implements Comparable<Student> {

    // Member variables of this class
    private int rollno;
    private String name;
    private Double marks;

    // Constructor of this class
    public Student(int rollno, String name, Double marks)
    {
        // This keyword refers to
        // current object itself

        this.rollno = rollno;
        this.name = name;
        this.marks = marks;
    }

    // Sorting based on marks of Students
    public int compareTo(Student s)
    {
        return this.marks.compareTo(s.marks);
    }

    public String toString()
    {
        return "Student{"
            + "RollNo=" + rollno + ", Name='" + name + '\''
            + ", Marks=" + marks + '}';
    }
}

// Class 2
// Main class
class GFG {

    // main driver method
    public static void main(String args[])
    {
        // Creating an ArrayList of user-defined
        // type(Student)
        ArrayList<Student> arr = new ArrayList<>();

        // Adding elements to object created above
        // Custom input entries
        arr.add(new Student(1, "Ankush", 98.0));
        arr.add(new Student(2, "Akshat", 99.0));
        arr.add(new Student(3, "Parul", 87.0));
        arr.add(new Student(4, "Tarun", 78.0));
        arr.add(new Student(5, "Swati", 90.0));

        // Iterating over the above ArrayList
        for (int i = 0; i < arr.size(); i++)

            // Print the ArrayList elements as
            // in order added
            System.out.println(arr.get(i));

        // Calling the Collection.sort() method
        // to sort elements od ArrayList
        Collections.sort(arr);

        // Printing the ArrayList after sorting
        System.out.println("\nAfter Sorting :\n");
        for (int i = 0; i < arr.size(); i++)
            System.out.println(arr.get(i));
    }
}
```

**输出**

```
Student{RollNo=1, Name='Ankush', Marks=98.0}
Student{RollNo=2, Name='Akshat', Marks=99.0}
Student{RollNo=3, Name='Parul', Marks=87.0}
Student{RollNo=4, Name='Tarun', Marks=78.0}
Student{RollNo=5, Name='Swati', Marks=90.0}

After Sorting :

Student{RollNo=4, Name='Tarun', Marks=78.0}
Student{RollNo=3, Name='Parul', Marks=87.0}
Student{RollNo=5, Name='Swati', Marks=90.0}
Student{RollNo=1, Name='Ankush', Marks=98.0}
Student{RollNo=2, Name='Akshat', Marks=99.0}
```
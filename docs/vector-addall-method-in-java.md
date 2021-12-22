# Java 中的 Vector addAll()方法

> 原文:[https://www.geeksforgeeks.org/vector-addall-method-in-java/](https://www.geeksforgeeks.org/vector-addall-method-in-java/)

*   **java.util.Vector.addAll(Collection C)**: This method is used to append all of the elements from the collection passed as a parameter to this function to the end of a vector keeping in mind the order of return by the collection’s iterator.

    **语法:**

    ```
    boolean addAll(Collection C)
    ```

    **参数:**该方法接受一个强制参数 **C** ，它是数组列表的集合。它是一个集合，其元素需要追加到向量的末尾。

    **返回值:**如果至少执行了一个追加动作，则该方法返回*真*，否则返回*假*。

    下面的程序说明了 Java.util.Vector.addAll()方法:

    ```
    // Java code to illustrate boolean addAll()
    import java.util.*;
    import java.util.ArrayList;

    public class GFG {
        public static void main(String args[])
        {

            // Creating an empty Vector
            Vector<String> vt = new Vector<String>();

            // Use add() method to add elements in the Vector
            vt.add("Geeks");
            vt.add("for");
            vt.add("Geeks");
            vt.add("10");
            vt.add("20");

            // A collection is created
            Collection<String> c = new ArrayList<String>();
            c.add("A");
            c.add("Computer");
            c.add("Portal");
            c.add("for");
            c.add("Geeks");

            // Displaying the Vector
            System.out.println("The Vector is: " + vt);

            // Appending the collection to the vector
            vt.addAll(c);

            // Clearing the vector using clear() and displaying
            System.out.println("The new vector is: " + vt);
        }
    }
    ```

    **Output:**

    ```
    The Vector is: [Geeks, for, Geeks, 10, 20]
    The new vector is: [Geeks, for, Geeks, 10, 20, A, Computer, Portal, for, Geeks]

    ```

*   **java.util.Vector.addAll(int index, Collection C)**: This method is used to append all of the elements from the collection passed as a parameter to this function at a specific index or position of a vector.

    **语法:**

    ```
    boolean addAll(int index, Collection C)
    ```

    **参数:**该函数接受两个参数，如上语法所示，描述如下。

    *   **索引**:该参数为整数数据类型，指定向量中从容器元素插入位置开始的位置。
    *   **C** :是数组列表的集合。它是需要追加元素的集合。

    **返回值:**如果至少执行了一个追加动作，则该方法返回*真*，否则返回*假*。

    下面的程序说明了 Java.util.Vector.addAll()方法:

    ```
    // Java code to illustrate boolean addAll()
    import java.util.*;
    import java.util.ArrayList;

    public class GFG {
        public static void main(String args[])
        {
            // Creating an empty Vector
            Vector<String> vt = new Vector<String>();

            // Use add() method to add elements in the Vector
            vt.add("Geeks");
            vt.add("for");
            vt.add("Geeks");
            vt.add("10");
            vt.add("20");

            // A collection is created
            Collection<String> c = new ArrayList<String>();
            c.add("A");
            c.add("Computer");
            c.add("Portal");
            c.add("for");
            c.add("Geeks");

            // Displaying the Vector
            System.out.println("The Vector is: " + vt);

            // Appending the collection to the vector
            vt.addAll(1, c);

            // Clearing the vector using clear() and displaying
            System.out.println("The new vector is: " + vt);
        }
    }
    ```

    **Output:**

    ```
    The Vector is: [Geeks, for, Geeks, 10, 20]
    The new vector is: [Geeks, A, Computer, Portal, for, Geeks, for, Geeks, 10, 20]

    ```
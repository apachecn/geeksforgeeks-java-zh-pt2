# Java 中的向量加法()方法

> 原文:[https://www.geeksforgeeks.org/vector-add-method-in-java/](https://www.geeksforgeeks.org/vector-add-method-in-java/)

*   **boolean add(Object element)**: This method appends the specified element to the end of this vector.

    **语法:**

    ```
    boolean add(Object element)
    ```

    **参数:**该函数接受单个参数**元素**，如上语法所示。由该参数指定的元素被附加到向量的末尾。

    **返回值:**此方法成功执行后返回**真**，否则**假**。

    下面的程序说明了 Java . util . vector . add(Object element)方法的工作原理:

    **示例:**

    ```
    // Java code to illustrate boolean add(Object element)
    import java.util.*;

    public class VectorDemo {
        public static void main(String args[])
        {

            // Creating an empty Vector
            Vector<String> vec_tor = new Vector<String>();

            // Use add() method to add elements in the vector
            vec_tor.add("Geeks");
            vec_tor.add("for");
            vec_tor.add("Geeks");
            vec_tor.add("10");
            vec_tor.add("20");

            // Output the present vector
            System.out.println("The vector is: " + vec_tor);

            // Adding new elements to the end
            vec_tor.add("Last");
            vec_tor.add("Element");

            // Printing the new vector
            System.out.println("The new Vector is: " + vec_tor);
        }
    }
    ```

    **Output:**

    ```
    The vector is: [Geeks, for, Geeks, 10, 20]
    The new Vector is: [Geeks, for, Geeks, 10, 20, Last, Element]

    ```

*   **void add(int index, Object element)**: This method inserts an element at a specified index in the vector. It shifts the element currently at that position (if any) and any subsequent elements to the right (will change their indices by adding one).

    **语法:**

    ```
    void add(int index, Object element)
    ```

    **参数:**该方法接受如下所述的两个参数。

    *   **索引:**要插入指定元素的索引。
    *   **元素:**需要插入的元素。

    **返回值:**此方法不返回值。

    **异常:**如果指定的索引超出向量大小的范围，该方法将抛出**indexout of boundsexception**。

    下面的程序说明了 java.util.Vector.add(int index，Object element)方法的工作原理:

    **示例:**

    ```
    // Java code to illustrate boolean add(Object element)
    import java.util.*;

    public class VectorDemo {
        public static void main(String args[])
        {

            // Creating an empty Vector
            Vector<String> vec_tor = new Vector<String>();

            // Use add() method to add elements in the vector
            vec_tor.add("Geeks");
            vec_tor.add("for");
            vec_tor.add("Geeks");
            vec_tor.add("10");
            vec_tor.add("20");

            // Output the present vector
            System.out.println("The vector is: " + vec_tor);

            // Adding new elements to the end
            vec_tor.add(2, "Last");
            vec_tor.add(4, "Element");

            // Printing the new vector
            System.out.println("The new Vector is: " + vec_tor);
        }
    }
    ```

    **Output:**

    ```
    The vector is: [Geeks, for, Geeks, 10, 20]
    The new Vector is: [Geeks, for, Last, Geeks, Element, 10, 20]

    ```
# Java 中的向量移除()方法

> 原文:[https://www.geeksforgeeks.org/vector-remove-method-in-java/](https://www.geeksforgeeks.org/vector-remove-method-in-java/)

*   ### 移除(整数索引)

    **T1。移除( *int index* )** 方法用于从特定位置或索引移除矢量中的元素。

    **语法:**

    ```
    Vector.remove(int index)
    ```

    **参数:**该方法接受一个强制参数**索引**为整数数据类型，并指定要从矢量中移除的元素的位置。

    **返回值:**这个方法返回刚刚从向量中移除的**元素**。

    下面的程序说明了 Java . util . vector . remove(int index)方法:

    ```
    // Java code to illustrate remove() when position of
    // element is passed as parameter
    import java.util.*;

    public class VectorDemo {
        public static void main(String args[])
        {

            // Creating an empty Vector
            Vector<String> vec_tor = new Vector<String>();

            // Use add() method to add elements in the Vector
            vec_tor.add("Geeks");
            vec_tor.add("for");
            vec_tor.add("Geeks");
            vec_tor.add("10");
            vec_tor.add("20");

            // Output the Vector
            System.out.println("Vector: " + vec_tor);

            // Remove the element using remove()
            String rem_ele = vec_tor.remove(4);

            // Print the removed element
            System.out.println("Removed element: " + rem_ele);

            // Print the final Vector
            System.out.println("Final Vector: " + vec_tor);
        }
    }
    ```

    **Output:**

    ```
    Vector: [Geeks, for, Geeks, 10, 20]
    Removed element: 20
    Final Vector: [Geeks, for, Geeks, 10]

    ```

*   ### 移除(对象 o)

    **T1。移除(的*对象)***方法用于从矢量中移除任何特定元素。

    **语法:**

    ```
    Vector.remove(Object o)
    ```

    **参数:**该方法接受一个强制参数 **o** 是矢量的对象类型，并指定要从矢量中移除的元素。

    **返回值:**如果找到指定元素并从向量中移除，则返回**真**，否则返回**假**。

    下面的程序说明了方法:

    ```
    // Java code to illustrate remove() method
    import java.util.*;

    public class VectorDemo {
        public static void main(String args[])
        {
            // Creating an empty Vector
            Vector<String> vec_tor = new Vector<String>();

            // Use add() method to add elements in the Vector
            vec_tor.add("Geeks");
            vec_tor.add("for");
            vec_tor.add("Geeks");
            vec_tor.add("10");
            vec_tor.add("20");

            // Output the Vector
            System.out.println("Vector: " + vec_tor);

            // Remove the head using remove()
            Boolean rem_ele;

            rem_ele = vec_tor.remove("Geeks");
            // Print the removed element
            if (rem_ele)
                System.out.println("Geeks"
                                   + " found and removed.");
            else
                System.out.println("Geeks"
                                   + " not found or removed.");

            rem_ele = vec_tor.remove("500");
            // Print the removed element
            if (rem_ele)
                System.out.println("500"
                                   + " found and removed.");
            else
                System.out.println("500"
                                   + " not found or removed.");

            // Print the final Vector
            System.out.println("Final Vector: " + vec_tor);
        }
    }
    ```

    **Output:**

    ```
    Vector: [Geeks, for, Geeks, 10, 20]
    Geeks found and removed.
    500 not found or removed.
    Final Vector: [for, Geeks, 10, 20]

    ```
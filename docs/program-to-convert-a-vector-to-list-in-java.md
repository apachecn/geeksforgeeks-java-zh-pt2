# 用 Java 将向量转换为列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-a-vector-to-list-in-Java/](https://www.geeksforgeeks.org/program-to-convert-a-vector-to-list-in-java/)

给定一个向量，任务是在 Java 中将向量转换为列表

**示例:**

```java
Input: Vector: [1, 2, 3, 4, 5]
Output: List: [1, 2, 3, 4, 5]

Input : Vector = [a, b, c, d, e, f]
Output : List  = [a, b, c, d, e, f]

```

*   **Using Collections.list() method**

    **语法:**

    ```java
    List list = Collections.list(vec.elements());

    ```

    **进场:**

    1.  获取向量
    2.  使用 collections . List(vector . elements())方法转换为列表，该方法返回对象列表。
    3.  打印列表

    下面是上述方法的实现:

    ```java
    // Java program to
    // convert vector to List

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a Vector of String elements
            Vector<String> vec = new Vector<String>();

            // Adding values of Vector
            vec.add("1");
            vec.add("2");
            vec.add("3");
            vec.add("4");
            vec.add("5");

            // print Vector elements
            System.out.println("Vector: " + vec);

            // Convert Vector to List
            List<String>
                list = Collections.list(vec.elements());

            // print List Elements
            System.out.println("List:" + list);
        }
    }
    ```

    **Output:**

    ```java
    Vector: [1, 2, 3, 4, 5]
    List:[1, 2, 3, 4, 5]

    ```

*   **Using Collection.unmodifiableList()**

    **语法:**

    ```java
    List list = Collections.unmodifiableList(vector);

    ```

    **进场:**

    1.  获取向量
    2.  使用 collections . unmodifieblelist(vector)方法转换为列表，该方法返回一个不可变的对象列表。
    3.  打印列表

    下面是上述方法的实现:

    ```java
    // Java program to
    // convert vector to List

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a Vector of String elements
            Vector<String> vec = new Vector<String>();

            // Adding values of Vector
            vec.add("1");
            vec.add("2");
            vec.add("3");
            vec.add("4");
            vec.add("5");

            // print Vector elements
            System.out.println("Vector: " + vec);

            // Convert Vector to List
            List<String>
                list = Collections.unmodifiableList(vec);

            // print List Elements
            System.out.println("List:" + list);
        }
    }
    ```

    **Output:**

    ```java
    Vector: [1, 2, 3, 4, 5]
    List:[1, 2, 3, 4, 5]

    ```

*   **Using constructor**

    **语法:**

    ```java
    List list = new ArrayList(vector);

    ```

    **进场:**

    1.  获取向量
    2.  通过将向量作为参数传递，从向量创建列表。
    3.  打印列表

    下面是上述方法的实现:

    ```java
    // Java program to
    // convert vector to List

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a Vector of String elements
            Vector<String> vec = new Vector<String>();

            // Adding values of Vector
            vec.add("1");
            vec.add("2");
            vec.add("3");
            vec.add("4");
            vec.add("5");

            // print Vector elements
            System.out.println("Vector: " + vec);

            // Convert Vector to List
            List<String>
                list = new ArrayList<String>(vec);

            // print List Elements
            System.out.println("List:" + list);
        }
    }
    ```

    **Output:**

    ```java
    Vector: [1, 2, 3, 4, 5]
    List:[1, 2, 3, 4, 5]

    ```
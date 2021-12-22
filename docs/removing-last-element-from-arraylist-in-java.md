# 从 Java 的数组列表中移除最后一个元素

> 原文:[https://www . geesforgeks . org/remove-last-element-from-ArrayList-in-Java/](https://www.geeksforgeeks.org/removing-last-element-from-arraylist-in-java/)

给定一个 Java 中的**数组列表**集合，任务是从数组列表中移除最后一个元素。

**例**:

```java
Input: ArrayList[] = [10, 20, 30, 1, 2]
Output: [10, 20, 30, 1]
After removing the last element 2, the ArrayList is:
[10, 20, 30, 1]

Input: ArrayList[] = [1, 1, 2, 2, 3]
Output: [1, 1, 2, 2]
After removing the last element 3, the ArrayList is:
[1, 1, 2, 2]

```

我们可以使用 Java 中 ArrayList 容器的 [remove()方法来移除最后一个元素。](https://www.geeksforgeeks.org/remove-element-arraylist-java/)

ArrayList 提供了两个重载的 remove()方法:

*   **移除(int index)** :接受待移除对象的索引。我们可以将最后一个元素索引传递给 remove()方法来删除最后一个元素。
*   **remove(Object obj)** : Accept object to be removed. If the ArrayList does not contain duplicates, we can simply pass the last element value to be deleted to the remove() method, and it will delete that value.

    **注意**:如果数组列表包含重复项，它将删除作为参数传递给 remove()方法的对象的第一个匹配项。

下面是使用两种方法删除最后一个元素的实现:

*   **程序 1** :使用移除(int index)。使用[大小()方法计算最后一个元素的指数](https://www.geeksforgeeks.org/arraylist-size-method-in-java-with-examples/)为:

    ```java
    index = ArrayList.size() - 1;

    ```

    ```java
    // Java program to delete last element of ArrayList
    import java.util.List;
    import java.util.ArrayList;

    public class GFG {
        public static void main(String[] args)
        {
            List<Integer> al = new ArrayList<>();
            al.add(10);
            al.add(20);
            al.add(30);
            al.add(1);
            al.add(2);

            // Calculate index of last element
            int index = al.size() - 1;

            // Delete last element by passing index
            al.remove(index);

            System.out.println("Modified ArrayList : " + al);
        }
    }
    ```

    **输出:**

    ```java
    Modified ArrayList : [10, 20, 30, 1]

    ```

*   **程序 2** :使用移除(对象对象)。

    ```java
    // Java program to delete last element of ArrayList
    import java.util.List;
    import java.util.ArrayList;

    public class GFG {
        public static void main(String[] args)
        {
            List<Integer> al = new ArrayList<>();
            al.add(10);
            al.add(20);
            al.add(30);
            al.add(1);
            al.add(2);

            // Since all elements are unique, pass the last
            // elements value to delete it
            // Note: values are integer object
            al.remove(new Integer(2));

            System.out.println("Modified ArrayList : " + al);
        }
    }
    ```

    **输出:**

    ```java
    Modified ArrayList : [10, 20, 30, 1]

    ```
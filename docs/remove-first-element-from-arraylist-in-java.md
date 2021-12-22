# 从 Java 的数组列表中移除第一个元素

> 原文:[https://www . geesforgeks . org/remove-first-element-from-ArrayList-in-Java/](https://www.geeksforgeeks.org/remove-first-element-from-arraylist-in-java/)

给定一个 Java 中的**数组列表**集合，任务是从数组列表中移除第一个元素。

**例**:

```
Input: ArrayList[] = [10, 20, 30, 1, 2]
Output: [20, 30, 1, 2]
After removing the first element 10, the ArrayList is:
[20, 30, 1, 2]

Input: ArrayList[] = [1, 1, 2, 2, 3]
Output: [1, 2, 2, 3]
After removing the first element 1, the ArrayList is:
[1, 2, 2, 3]

```

我们可以使用 Java 中 ArrayList 容器的 [remove()方法来移除第一个元素。](https://www.geeksforgeeks.org/remove-element-arraylist-java/)

ArrayList 提供了两个重载的 remove()方法:

*   **移除(int index)** :接受待移除对象的索引。我们可以将第一个元素的索引传递给 remove()方法来删除第一个元素。
*   **remove(Object obj)** : Accept object to be removed. If the ArrayList does not contain duplicates, we can simply pass the first element value as an object to be deleted to the remove() method, and it will delete that value.

    **注意**:如果数组列表包含重复项，它将删除作为参数传递给 remove()方法的对象的第一个匹配项。

下面是使用两种方法删除第一个元素的实现:

*   **程序 1** :使用移除(int index)。数组列表中元素的索引从零开始。因此，数组列表中第一个元素的索引是 0。

    ```
    // Java program to delete the first element of ArrayList
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

            // First element's index is always 0
            int index = 0;

            // Delete first element by passing index
            al.remove(index);

            System.out.println("Modified ArrayList : " + al);
        }
    }
    ```

    **输出:**

    ```
    Modified ArrayList : [20, 30, 1, 2]

    ```

*   **程序 2** :使用移除(对象对象)。

    ```
    // Java program to delete first element of ArrayList
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

            // Since all elements are unique, pass the first
            // elements value to delete it
            // Note: values are integer object
            al.remove(new Integer(10));

            System.out.println("Modified ArrayList : " + al);
        }
    }
    ```

    **输出:**

    ```
    Modified ArrayList : [20, 30, 1, 2]

    ```
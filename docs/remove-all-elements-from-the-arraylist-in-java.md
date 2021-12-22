# 从 Java 的数组列表中移除所有元素

> 原文:[https://www . geesforgeks . org/remove-all-elements-from-ArrayList-in-Java/](https://www.geeksforgeeks.org/remove-all-elements-from-the-arraylist-in-java/)

**先决条件:**[Java 中的数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)

给定一个数组列表，任务是移除 Java 中数组列表的所有元素。

**示例:**

```
Input: ArrayList = [1, 2, 3, 4] 
Output: ArrayList = [] 

Input: ArrayList = [12, 23, 34, 45, 57, 67, 89] 
Output: ArrayList = [] 

```

*   **Using clear() method:**

    **语法:**

    ```
    collection_name.clear();
    ```

    **清除()方法代码:**

    ```
    public void clear() {
        for (int i = 0; i < size; i++)
            list[i] = null;

        size = 0;
    }

    ```

    下面是上述方法的实现:

    ```
    // Java Program for remove all elements ArrayList
    // Using clear() method

    // import  ArrayList package
    import java.util.ArrayList;

    public class GFG {

        // main method
        public static void main(String[] args)
        {
            // create empty ArrayList
            ArrayList<String> list = new ArrayList<>();

            // Adding elements of list
            list.add("Geeks");
            list.add("for");
            list.add("Geeks");
            list.add("Gaurav");

            // printing initial value ArrayList
            System.out.println("ArrayList: " + list);

            // print size of ArrayList
            System.out.println("Size of ArrayList = "
                               + list.size());

            // remove all elements using clear() method
            list.clear();

            // printing ArrayList
            System.out.println("\nAfter clear\n\n"
                             + "ArrayList: " + list);

            // print size of ArrayList after clear list
            System.out.println("Size of ArrayList = "
                               + list.size());
        }
    }
    ```

    **Output:**

    ```
    ArrayList: [Geeks, for, Geeks, Gaurav]
    Size of ArrayList = 4

    After clear

    ArrayList: []
    Size of ArrayList = 0

    ```

    **时间复杂度:O(N)**

*   **Using removeAll() method**

    **语法:**

    ```
    collection_name.removeAll(collection_name);
    ```

    **remove all()方法代码:**

    ```
    public boolean removeAll(Collection list) {
        boolean isModi = false;
        Iterator ite= iterator();
        while (ite.hasNext()) {
            if (list.contains(ite.next())) {
                ite.remove();
                isModi = true;
            }
        }
        return isModi;
    }

    ```

    下面是上述方法的实现:

    ```
    // Java Program for remove all elements ArrayList
    // Using removeAll() method

    // import  ArrayList package
    import java.util.ArrayList;

    public class GFG {

        // main method
        public static void main(String[] args)
        {
            // create empty ArrayList
            ArrayList<String> list = new ArrayList<>();

            // Adding elements of list
            list.add("Geeks");
            list.add("for");
            list.add("Geeks");
            list.add("Gaurav");

            // printing initial value ArrayList
            System.out.println("ArrayList: " + list);

            // print size of ArrayList
            System.out.println("Size of ArrayList = "
                               + list.size());

            // remove all elements using clear() method
            list.removeAll(list);

            // printing ArrayList
            System.out.println("\nAfter clear\n\n"
                             + "ArrayList: " + list);

            // print size of ArrayList after clear list
            System.out.println("Size of ArrayList = "
                               + list.size());
        }
    }
    ```

    **Output:**

    ```
    ArrayList: [Geeks, for, Geeks, Gaurav]
    Size of ArrayList = 4

    After clear

    ArrayList: []
    Size of ArrayList = 0

    ```

    **时间复杂度:O(N^2)**
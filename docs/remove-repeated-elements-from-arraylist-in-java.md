# 从 Java 的数组列表中移除重复的元素

> 原文:[https://www . geesforgeks . org/remove-repeated-elements-from-ArrayList-in-Java/](https://www.geeksforgeeks.org/remove-repeated-elements-from-arraylist-in-java/)

**先决条件:**Java 中的[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)

给定一个数组列表，任务是删除 Java 中数组列表的重复元素。

**例:**

```
Input: ArrayList = [1, 2, 2, 3, 4, 4, 4] 
Output: [1, 2, 3, 4] 

Input: ArrayList = [12, 23, 23, 34, 45, 45, 45, 45, 57, 67, 89] 
Output: [12, 23, 34, 45, 57, 67, 89]

```

以下是在 Java 中移除数组列表中重复元素的各种方法:

*   **Using a Set:** Since Set is a collection which do not includes any duplicate elements. Hence the solution can be achieved with the help of a Set.

    **方法:**

    1.  Gets an array list with duplicate elements.
    2.  Convert an array list to a collection.
    3.  Now convert the collection back to an array list. This will delete all duplicate elements.

    下面是上面方法的实现:

    ```
    // Java code to illustrate remove duolicate
    // of ArrayList using hashSet<> method

    import java.util.*;

    public class GFG {
        public static void main(String args[])
        {

            // create a ArrayList String type
            ArrayList<String>
                gfg = new ArrayList<String>();

            // Initialize an ArrayList
            gfg.add("Geeks");
            gfg.add("for");
            gfg.add("Geeks");

            // print ArrayList
            System.out.println("Original ArrayList : "
                               + gfg);

            // -----Using LinkedHashSet-----
            System.out.println("\nUsing LinkedHashSet:\n");

            // create a set and copy all value of list
            Set<String> set = new LinkedHashSet<>(gfg);

            // create a list and copy all value of set
            List<String> gfg1 = new ArrayList<>(set);

            // print ArrayList
            System.out.println("Modified ArrayList : "
                               + gfg1);

            // -----Using HashSet-----
            System.out.println("\nUsing HashSet:\n");

            // create a set and copy all value of list
            Set<String> set1 = new HashSet<>(gfg);

            // create a list and copy all value of set
            List<String> gfg2 = new ArrayList<>(set);

            // print ArrayList
            System.out.println("Modified ArrayList : "
                               + gfg2);
        }
    }
    ```

    **输出:**

    ```
    Original ArrayList : [Geeks, for, Geeks]

    Using LinkedHashSet:

    Modified ArrayList : [Geeks, for]

    Using HashSet:

    Modified ArrayList : [Geeks, for]

    ```

*   **使用 Java 8 Lambdas:**

    **方法:**

    1.  Get ArrayList with duplicate elements.
    2.  Use the Stream () method to convert the array list into a stream.
    3.  Use the distinct () method to set the filter condition to distinct.
    4.  Use the Collect () method to collect the filtered values as a list. The list will have the of duplicate elements.

    删除，下面是上述方法的实现:

    **示例:**

    ```
    // Java code to illustrate remove duolicate
    // of ArrayList using hashSet<> method

    import java.util.*;
    import java.util.stream.Collectors;

    public class GFG {
        public static void main(String args[])
        {
            // create a ArrayList String type
            ArrayList<String>
                gfg = new ArrayList<String>();

            // Initialize an ArrayList
            gfg.add("Geeks");
            gfg.add("for");
            gfg.add("Geeks");

            // print ArrayList
            System.out.println("Original ArrayList : "
                               + gfg);

            // create a list and copy all distinct value of list
            List<String> gfg1 = gfg.stream()
                                    .distinct()
                                    .collect(Collectors.toList());

            // print modified list
            System.out.println("Modified List : " + gfg1);
        }
    }
    ```

    **输出:**

    ```
    Original ArrayList : [Geeks, for, Geeks]
    Modified List : [Geeks, for]

    ```
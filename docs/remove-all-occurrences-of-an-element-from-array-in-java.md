# 从 Java 中的数组中移除所有出现的元素

> 原文:[https://www . geesforgeks . org/从 java 数组中移除所有出现的元素/](https://www.geeksforgeeks.org/remove-all-occurrences-of-an-element-from-array-in-java/)

给定一个数组和一个键，任务是在 Java 中从数组中移除指定键的所有出现。

示例:

```java
Input: array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 }, key = 3
Output: [9, 2, 1, 7, 2, 5]

Input: array = { 10, 20, 10, 30, 50, 10 }, key = 10
Output: [20, 30, 50]

```

1.  ### Use [array to copy](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/) :

    ```java
    // Java program remove all occurrences
    // of an element from Array using naive method

    import java.util.Arrays;

    class GFG {

        // function to remove all occurrences
        // of an element from an array
        public static int[] removeElements(int[] arr, int key)
        {
              // Move all other elements to beginning 
              int index = 0;
              for (int i=0; i<arr.length; i++)
                 if (arr[i] != key)
                    arr[index++] = arr[i];

             // Create a copy of arr[] 
             return Arrays.copyOf(arr, index);
        }

        // Driver code
        public static void main(String[] args)
        {
            int[] array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 };
            int key = 3;
            array = removeElements(array, key);
            System.out.println(Arrays.toString(array));
        }
    }
    ```

    **Output:**

    ```java
    [9, 2, 1, 7, 2, 5]

    ```

    1.  ### 使用 Java 8 流:

        1.  获取数组和密钥。
        2.  过滤列表中等于给定关键字的所有元素
        3.  将列表转换回数组并返回。

        下面是上述方法的实现:

        ```java
        // Java program remove all occurrences
        // of an element from Array
        // Using Java 8 Stream API

        import java.util.Arrays;

        class GFG {

            // function to remove all occurrences
            // of an element from an array
            public static int[] removeElements(int[] arr, int key)
            {

                // return a new array except given key
                return Arrays.stream(arr)
                    .filter(val -> val != key)
                    .toArray();
            }

            // Driver code
            public static void main(String[] args)
            {

                // Get the array
                int[] array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 };

                // Get the key
                int key = 3;

                // Remove the key
                array = removeElements(array, key);

                // Print the modified array
                System.out.println(Arrays.toString(array));
            }
        }
        ```

        **Output:**

        ```java
        [9, 2, 1, 7, 2, 5]

        ```

    2.  ### 使用 Java 数组列表:

        1.  获取数组和密钥。
        2.  创建一个空数组列表
        3.  将数组中除指定键以外的所有元素插入列表
        4.  将列表转换回数组并返回。

        下面是上述方法的实现:

        **程序:**

        ```java
        // Java program remove all occurrences
        // of an element from Array
        // Using Java ArrayLists

        import java.util.*;

        class GFG {

            // function to remove all occurrences
            // of an element from an array
            public static int[] removeElements(int[] arr, int key)
            {

                // create an empty ArrayList
                List<Integer> result = new ArrayList<Integer>();

                // insert all elements from the array into the list
                // except the specified key
                for (int i : arr) {
                    if (i != key) {
                        result.add(i);
                    }
                }

                // convert the list back to an array and return it
                return result.stream()
                    .mapToInt(Integer::intValue)
                    .toArray();
            }

            // Driver code
            public static void main(String[] args)
            {

                // Get the array
                int[] array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 };

                // Get the key
                int key = 3;

                // Remove the key
                array = removeElements(array, key);

                // Print the modified array
                System.out.println(Arrays.toString(array));
            }
        }
        ```

        **Output:**

        ```java
        [9, 2, 1, 7, 2, 5]

        ```

    3.  ### Alternative method:

        1.  首先创建一个数组列表。
        2.  将数组中的所有元素移除到指定键所在的列表中。
        3.  Convert the list back to an array and return its.

            下面是上述方法的实现:

            **程序:**

            ```java
            // Java program remove all occurrences
            // of an element from Array
            // Using Java List

            import java.util.Arrays;
            import java.util.List;
            import java.util.stream.Collectors;
            import java.util.stream.IntStream;

            class GFG {

                // function to remove all occurrences
                // of an element from an array
                public static int[] removeElements(int[] arr, int key)
                {

                    // Create a List
                    // Insert all element of array into List
                    List<Integer> result = IntStream.of(arr) // IntStream
                                               .boxed()
                                               .collect(Collectors.toList());

                    // check every element if found then remove
                    for (int i = 0; i < result.size(); i++) {
                        if (result.get(i).equals(key)) {
                            result.remove(i--);
                        }
                    }

                    // convert the list back to an array and return it
                    return result.stream()
                        .mapToInt(Integer::intValue)
                        .toArray();
                }

                // Driver code
                public static void main(String[] args)
                {

                    // Get the array
                    int[] array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 };

                    // Get the key
                    int key = 3;

                    // Remove the key
                    array = removeElements(array, key);

                    // Print the modified array
                    System.out.println(Arrays.toString(array));
                }
            }
            ```

            **Output:**

            ```java
            [9, 2, 1, 7, 2, 5]

            ```

        4.  ### 使用 List.removeAll():

            1.  首先创建一个空的数组列表。
            2.  将数组的所有元素插入列表
            3.  移除所有要移除的元素
            4.  将列表转换回数组并返回其。

            下面是上述方法的实现:

            **程序:**

            ```java
            // Java program remove all occurrences
            // of an element from Array

            import java.util.*;
            import java.util.stream.*;

            class GFG {

                // function to remove all occurrences of key
                public static int[] removeElements(int[] arr, int key)
                {

                    // Create a List
                    // Insert all element of array into List
                    List<Integer> result = IntStream.of(arr) // IntStream
                                               .boxed()
                                               .collect(Collectors.toList());

                    // remove all specific values and
                    // an immutable set containing only the specified object
                    result.removeAll(Collections.singleton(key));

                    // sequential Stream over the elements in this collection
                    // and return a new array
                    return result.stream()
                        .mapToInt(Integer::intValue)
                        .toArray();
                }

                // Driver code
                public static void main(String[] args)
                {

                    // Get the array
                    int[] array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 };

                    // Get the key
                    int key = 3;

                    // Remove the key
                    array = removeElements(array, key);

                    // Print the modified array
                    System.out.println(Arrays.toString(array));
                }
            }
            ```

            **Output:**

            ```java
            [9, 2, 1, 7, 2, 5]

            ```

        5.  ### 使用 List.removeIf():

            1.  首先创建一个空的数组列表。
            2.  将数组的所有元素插入列表
            3.  使用 equals()方法移除所有要移除的元素
            4.  将列表转换回数组并返回其。

            下面是上述方法的实现:

            **程序:**

            ```java
            // Java program remove all occurrences
            // of an element from Array

            import java.util.*;
            import java.util.stream.*;

            class GFG {

                // function to remove all occurrences of key
                public static int[] removeElements(int[] arr, int key)
                {

                    // Create a List
                    // Insert all element of array into List
                    List<Integer> result = IntStream.of(arr) // IntStream
                                               .boxed()
                                               .collect(Collectors.toList());

                    // remove all specific values if match
                    result.removeIf(n -> (n.equals(key)));

                    // convert list into new array and return
                    return result.stream()
                        .mapToInt(Integer::intValue)
                        .toArray();
                }

                // Driver code
                public static void main(String[] args)
                {

                    // Get the array
                    int[] array = { 3, 9, 2, 3, 1, 7, 2, 3, 5 };

                    // Get the key
                    int key = 3;

                    // Remove the key
                    array = removeElements(array, key);

                    // Print the modified array
                    System.out.println(Arrays.toString(array));
                }
            }
            ```

            **Output:**

            ```java
            [9, 2, 1, 7, 2, 5]

            ```
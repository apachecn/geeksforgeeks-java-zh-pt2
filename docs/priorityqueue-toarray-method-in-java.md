# Java 中的 PriorityQueue toArray()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-to array-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-toarray-method-in-java/)

1.  The **java.util.PriorityQueue.toArray()** method in Java is used to form an array of the same elements as that of the Priority Queue. Basically, it copies all the element from a priority queue to a new array.

    **语法:**

    ```java
    Object[] arr = Priority_Queue.toArray()
    ```

    **参数:**该方法不取任何参数。

    **返回值:**该方法返回一个数组，该数组包含类似于优先级队列的元素。

    下面的程序说明了 Java . util . priorityqueue . toarray()方法。
    **节目一:**

    ```java
    // Java code to illustrate toArray()
    import java.util.*;

    public class PriorityQueueDemo {
        public static void main(String args[])
        {
            // Creating an empty PriorityQueue
            PriorityQueue<String> queue = new PriorityQueue<String>();

            // Use add() method to add elements into the Queue
            queue.add("Welcome");
            queue.add("To");
            queue.add("Geeks");
            queue.add("For");
            queue.add("Geeks");

            // Displaying the PriorityQueue
            System.out.println("The PriorityQueue: " + queue);

            // Creating the array and using toArray()
            Object[] arr = queue.toArray();

            System.out.println("The array is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
    }
    ```

    **Output:**

    ```java
    The PriorityQueue: [For, Geeks, To, Welcome, Geeks]
    The array is:
    For
    Geeks
    To
    Welcome
    Geeks

    ```

    **程序 2:**

    ```java
    // Java code to illustrate toArray()
    import java.util.*;

    public class PriorityQueueDemo {
        public static void main(String args[])
        {
            // Creating an empty PriorityQueue
            PriorityQueue<Integer> queue = new PriorityQueue<Integer>();

            // Use add() method to add elements into the Queue
            queue.add(10);
            queue.add(15);
            queue.add(30);
            queue.add(20);
            queue.add(5);
            queue.add(25);

            // Displaying the PriorityQueue
            System.out.println("The PriorityQueue: " + queue);

            // Creating the array and using toArray()
            Object[] arr = queue.toArray();

            System.out.println("The array is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
    }
    ```

    **Output:**

    ```java
    The PriorityQueue: [5, 10, 25, 20, 15, 30]
    The array is:
    5
    10
    25
    20
    15
    30

    ```

2.  The **java.util.PriorityQueue.toArray(arr[])** method in Java is used to form an array of the same elements as that of the Priority Queue. Basically, it copies all the element from a priority queue to a new array. It creates multiple arrays, unlike the previous method without parameters. This method copies all of the elements into the arr[].
    **Syntax:**

    ```java
    Object[] arr1 = Priority_Queue.toArray(arr[])
    ```

    **参数:**该方法接受一个参数 *arr[]* ，队列的所有元素都将被复制到该参数中。

    **返回值:**该方法返回一个数组，该数组包含类似于优先级队列的元素。

    **Exception:**

3.  ArrayStoreException:当提到的数组属于不同的类型，并且不能与队列中提到的元素进行比较时。
4.  NullPointerException: If the array is Null, then this exception is thrown.

    下面的程序说明了 Java . util . priorityqueue . to array(arr[])方法的工作原理。

    ```java
    // Java code to illustrate toArray(arr[])
    import java.util.*;

    public class PriorityQueueDemo {
        public static void main(String args[])
        {
            // Creating an empty PriorityQueue
            PriorityQueue<String> queue = new PriorityQueue<String>();

            // Use add() method to add elements into the Queue
            queue.add("Welcome");
            queue.add("To");
            queue.add("Geeks");
            queue.add("For");
            queue.add("Geeks");

            // Displaying the PriorityQueue
            System.out.println("The PriorityQueue: " + queue);

            // Creating the array and using toArray()
            String[] arr = new String[5];
            String[] arr1 = queue.toArray(arr);

            // Displaying arr
            System.out.println("The arr[] is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);

            // Displaying arr1
            System.out.println();    
            System.out.println("The arr1[] is:");
            for (int i = 0; i < arr1.length; i++)
                System.out.println(arr1[i]);
        }
    }
    ```

    **Output:**

    ```java
    The PriorityQueue: [For, Geeks, To, Welcome, Geeks]
    The arr[] is:
    For
    Geeks
    To
    Welcome
    Geeks

    The arr1[] is:
    For
    Geeks
    To
    Welcome
    Geeks

    ```
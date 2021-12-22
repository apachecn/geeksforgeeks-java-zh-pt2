# 用 Java 将地图转换成流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-a-map-a-stream-in-Java/](https://www.geeksforgeeks.org/program-to-convert-a-map-to-a-stream-in-java/)

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。

以下是用 Java 将地图转换为流各种方法:

1.  **Converting complete Map<Key, Value> into Stream**: This can be done with the help of Map.entrySet() method which returns a Set view of the mappings contained in this map. In Java 8, this returned set can be easily converted into a Stream of key-value pairs using Set.stream() method.

    **算法**:

    1.  获取地图<key value="">。</key>
    2.  使用 Map.entrySet()方法将地图<key value="">转换为集合<key>。</key></key>
    3.  使用 Set.stream()将获得的集合转换为流
    4.  返回/打印地图流。

    **程序:**

    ```
    // Java Program to convert
    // Map<Key, Value> into Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert List of
        // String to List of Integer
        public static <K, V> Stream<Map.Entry<K, V> >
        convertMapToStream(Map<K, V> map)
        {

            // Return the obtained Stream
            return map

                // Convert the Map to Set
                .entrySet()

                // Convert the Set to Stream
                .stream();
        }

        public static void main(String args[])
        {

            // Create a Map
            Map<Integer, String> map = new HashMap<>();

            // Add entries to the Map
            map.put(1, "Geeks");
            map.put(2, "forGeeks");
            map.put(3, "A computer Portal");

            // Print the Map
            System.out.println("Map: " + map);

            // Convert the Map to Stream
            Stream<Map.Entry<Integer, String> > stream = 
                                       convertMapToStream(map);

            // Print the TreeMap
            System.out.println("Stream: " 
                          + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Map: {1=Geeks, 2=forGeeks, 3=A computer Portal}
    Stream: [1=Geeks, 2=forGeeks, 3=A computer Portal]

    ```

2.  **Converting only the Keyset of the Map<Key, Value> into Stream**: This can be done with the help of Map.keySet() method which returns a Set view of the keys contained in this map. In Java 8, this returned set can be easily converted into a Stream of key-value pairs using Set.stream() method.

    **算法**:

    1.  获取地图<key value="">。</key>
    2.  使用 Map.keySet()方法将地图<key value="">转换为集合<key>。</key></key>
    3.  使用 Set.stream()将获得的集合转换为流
    4.  返回/打印地图流。

    **程序:**

    ```
    // Java Program to convert
    // Map<Key, Value> into Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert List of
        // String to List of Integer
        public static <K, V> Stream<K>
        convertMapToStream(Map<K, V> map)
        {

            // Return the obtained Stream
            return map

                // Convert the Map to Set<Key>
                .keySet()

                // Convert the Set to Stream
                .stream();
        }

        public static void main(String args[])
        {

            // Create a Map
            Map<Integer, String> map = new HashMap<>();

            // Add entries to the Map
            map.put(1, "Geeks");
            map.put(2, "forGeeks");
            map.put(3, "A computer Portal");

            // Print the Map
            System.out.println("Map: " + map);

            // Convert the Map to Stream
            Stream<Integer> stream = convertMapToStream(map);

            // Print the TreeMap
            System.out.println("Stream: " 
                        + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Map: {1=Geeks, 2=forGeeks, 3=A computer Portal}
    Stream: [1, 2, 3]

    ```

3.  **Converting only the Value of the Map<Key, Value> into Stream**: This can be done with the help of Map.values() method which returns a Set view of the values contained in this map. In Java 8, this returned set can be easily converted into a Stream of key-value pairs using Set.stream() method.

    **算法**:

    1.  获取地图<key value="">。</key>
    2.  使用 Map.values()方法将地图<key value="">转换为集合<value>。</value></key>
    3.  使用 Set.stream()将获得的集合转换为流
    4.  返回/打印地图流。

    **程序:**

    ```
    // Java Program to convert
    // Map<Key, Value> into Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert List of
        // String to List of Integer
        public static <K, V> Stream<V>
        convertMapToStream(Map<K, V> map)
        {

            // Return the obtained Stream
            return map

                // Convert the Map to Set<Value>
                .values()

                // Convert the Set to Stream
                .stream();
        }

        public static void main(String args[])
        {

            // Create a Map
            Map<Integer, String> map = new HashMap<>();

            // Add entries to the Map
            map.put(1, "Geeks");
            map.put(2, "forGeeks");
            map.put(3, "A computer Portal");

            // Print the Map
            System.out.println("Map: " + map);

            // Convert the Map to Stream
            Stream<String> stream = convertMapToStream(map);

            // Print the TreeMap
            System.out.println("Stream: " 
                         + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Map: {1=Geeks, 2=forGeeks, 3=A computer Portal}
    Stream: [Geeks, forGeeks, A computer Portal]

    ```
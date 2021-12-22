# 用 Java 将列表转换为地图的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-list-to-map-in-Java/](https://www.geeksforgeeks.org/program-to-convert-list-to-map-in-java/)

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是收藏的子界面。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[链表](https://www.geeksforgeeks.org/linked-list-in-java/)、[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)和[栈](https://www.geeksforgeeks.org/stack-class-in-java/)类实现。

[java.util.Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口表示键和值之间的映射。地图界面不是[收藏](https://www.geeksforgeeks.org/collections-in-java-2/)界面的子类型。因此，它的行为与其他集合类型有些不同。
![mapinterface](img/b0646a8669bed97bdcc9a305ccd77d0d.png)

**示例:**

```java
Input: List : [1="1", 2="2", 3="3"]
Output: Map : {1=1, 2=2, 3=3}

Input: List : [1="Geeks", 2="for", 3="Geeks"]
Output: Map : {1=Geeks, 2=for, 3=Geeks}

```

下面是用 Java 将列表转换为地图的各种方法。为此，假设列表的每个元素都有一个标识符，该标识符将在生成的地图中用作关键字。

1.  **Using by object of list:**

    **进场:**

    1.  获取要转换为地图的列表
    2.  创建一个空地图
    3.  遍历列表中的项目，并将它们添加到地图中。
    4.  返回形成的地图

    ```java
    // Java program for list convert in map
    // with the help of Object method

    import java.util.ArrayList;
    import java.util.List;
    import java.util.Map;
    import java.util.HashMap;

    // create a list
    class Student {

        // id will act as Key
        private Integer id;

        // name will act as value
        private String name;

        // create curstuctor for reference
        public Student(Integer id, String name)
        {

            // assign the value of id and name
            this.id = id;
            this.name = name;
        }

        // return private variable id
        public Integer getId()
        {
            return id;
        }

        // return private variable name
        public String getName()
        {
            return name;
        }
    }

    // main class and method
    public class GFG {

        // main Driver
        public static void main(String[] args)
        {

            // create a list
            List<Student>
                lt = new ArrayList<Student>();

            // add the member of list
            lt.add(new Student(1, "Geeks"));
            lt.add(new Student(2, "For"));
            lt.add(new Student(3, "Geeks"));

            // create map with the help of
            // Object (stu) method
            // create object of Map class
            Map<Integer, String> map = new HashMap<>();

            // put every value list to Map
            for (Student stu : lt) {
                map.put(stu.getId(), stu.getName());
            }

            // print map
            System.out.println("Map  : " + map);
        }
    }
    ```

    **Output:**

    ```java
    Map  : {1=Geeks, 2=For, 3=Geeks}

    ```

2.  **使用 Collectors.toMap()方法:**该方法包括创建学生对象列表，并使用 Collectors.toMap()将其转换为地图。
    **进场:**

    ```java
    // Java program for list convert  in map
    // with the help of Collectors.toMap() method

    import java.util.ArrayList;
    import java.util.LinkedHashMap;
    import java.util.List;
    import java.util.stream.Collectors;

    // create a list
    class Student {

        // id will act as Key
        private Integer id;

        // name will act as value
        private String name;

        // create curstuctor for reference
        public Student(Integer id, String name)
        {

            // assign the value of id and name
            this.id = id;
            this.name = name;
        }

        // return private variable id
        public Integer getId()
        {
            return id;
        }

        // return private variable name
        public String getName()
        {
            return name;
        }
    }

    // main class and method
    public class GFG {

        // main Driver
        public static void main(String[] args)
        {

            // create a list
            List<Student> lt = new ArrayList<>();

            // add the member of list
            lt.add(new Student(1, "Geeks"));
            lt.add(new Student(2, "For"));
            lt.add(new Student(3, "Geeks"));

            // create map with the help of
            // Collectors.toMap() method
            LinkedHashMap<Integer, String>
                map = lt.stream()
                          .collect(
                              Collectors
                                  .toMap(
                                      Student::getId,
                                      Student::getName,
                                      (x, y)
                                          -> x + ", " + y,
                                      LinkedHashMap::new));

            // print map
            map.forEach(
                (x, y) -> System.out.println(x + "=" + y));
        }
    }
    ```

    **出场:**

    ```java
    1=Geeks
    2=For
    3=Geeks

    ```

    1.  获取要转换为地图的列表
    2.  使用 List.stream()方法将列表转换为流
    3.  借助 Collectors.toMap()方法创建地图
    4.  使用 stream.collect()方法收集形成的地图
    5.  返回形成的地图
3.  **Creating MultiMap using Collectors.groupingBy():**

    **进场:**

    1.  获取要转换为地图的列表
    2.  使用 List.stream()方法将列表转换为流
    3.  借助 Collectors.groupingBy()方法创建地图
    4.  使用 stream.collect()方法收集形成的地图
    5.  返回形成的地图

    ```java
    // Java program for list convert  in map
    // with the help of Collectors.groupingBy() method

    import java.util.*;
    import java.util.stream.Collectors;

    // create a list
    class Student {

        // id will act as Key
        private Integer id;

        // name will act as value
        private String name;

        // create curstuctor for reference
        public Student(Integer id, String name)
        {

            // assign the value of id and name
            this.id = id;
            this.name = name;
        }

        // return private variable id
        public Integer getId()
        {
            return id;
        }

        // return private variable name
        public String getName()
        {
            return name;
        }
    }

    // main class and method
    public class GFG {

        // main Driver
        public static void main(String[] args)
        {

            // create a list
            List<Student> lt = new ArrayList<Student>();

            // add the member of list
            lt.add(new Student(1, "Geeks"));
            lt.add(new Student(1, "For"));
            lt.add(new Student(2, "Geeks"));
            lt.add(new Student(2, "GeeksForGeeks"));

            // create map with the help of
            // Object (stu) method
            // create object of Multi Map class

            // create multimap and store the value of list
            Map<Integer, List<String> >
                multimap = lt
                               .stream()
                               .collect(
                                   Collectors
                                       .groupingBy(
                                           Student::getId,
                                           Collectors
                                               .mapping(
                                                   Student::getName,
                                                   Collectors
                                                       .toList())));

            // print the multiMap
            System.out.println("MultiMap = " + multimap);
        }
    }
    ```

    **Output:**

    ```java
    MultiMap = {1=[Geeks, For], 2=[Geeks, GeeksForGeeks]}

    ```
# 使用树形图对 Java 中的用户定义对象进行排序

> 原文:[https://www . geesforgeks . org/using-tree map-to-sort-user-defined-objects-in-Java/](https://www.geeksforgeeks.org/using-treemap-to-sort-user-defined-objects-in-java/)

给定的示例显示了如何对用户定义的对象进行排序 TreeMap，您可以根据方法内部提供的逻辑对键进行排序。
给定一条正整数形式的员工姓名和工资记录，需要根据员工工资对记录进行排序，使用 Java 中的[树形图](https://www.geeksforgeeks.org/treemap-in-java/)。如果工资相同，则使用员工姓名进行比较。

**示例:**

```java
Input : xbnnskd 100 geek 50
Output : geek 50 xbnnskd 100

Input : shyam 50 ram 50
Output : ram 50 shyam 50
Explanation : 
As both the employees have equal pay, 
sorting is done on the basis of employee's name.

```

**进场:**

```java
1\. Traverse through the string 
   and map the employee's salary(S)
   with the list of employee names having salary S.
2\. Use a TreeMap to have 
   keys(Employee's Salary) in a sorted manner.
3\. Now, Traverse through the map 
   and print the sorted records.

```

下面是上述方法的实现:

```java
// Java program to print employees
// records in a sorted manner

import java.io.*;
import java.util.*;

public class GFG {

    // Function to sort the records
    static void sortRecords(String records)
    {

        // split the string
        // on the basis of delimiter space(" ")
        String[] rec = records.split(" ");

        // Create a Treemap to store
        // employee's salary with employee's name
        Map<Integer, ArrayList<String> > map = new TreeMap<>();

        // Traverse the records array
        // and store values in map
        for (int i = 1; i < rec.length; i += 2) {

            // Converting String to integer
            int sal = Integer.parseInt(rec[i]);

            String name = rec[i - 1];

            if (map.containsKey(sal)) {

                ArrayList<String> al = map.get(sal);
                al.add(name);

                // Sorting list of employees having Salary sal
                Collections.sort(al);
                map.remove(sal);
                map.put(sal, al);
            }
            else {
                ArrayList<String> al = new ArrayList<>();
                al.add(name);
                map.put(sal, al);
            }
        }

        // Traversing the map
        // to print the sorted records
        for (Map.Entry<Integer,
                       ArrayList<String> >
                 entry : map.entrySet()) {

            ArrayList<String> al1 = entry.getValue();

            for (int i = 0; i < al1.size(); i++)
                System.out.print(al1.get(i) + " "
                                 + entry.getKey() + " ");
        }
    }

    // Driver code
    public static void main(String args[])
    {
       String records = "Harsh 100 Neha 100 Neha 20 Samay 600 Karan 50";
        // Calling function to sort the records
        sortRecords(records);
    }
}
```

**Output:**

```java
Neha 20 Karan 50 Harsh 100 Neha 100 Samay 600

```
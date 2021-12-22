# Java 中的 Vector removeIf()方法

> 原文:[https://www . geesforgeks . org/vector-removeif-method-in-Java/](https://www.geeksforgeeks.org/vector-removeif-method-in-java/)

的 **removeIf()** 方法从矢量中移除所有满足作为参数传递给该方法的条件的元素。如果从向量中移除了某些元素，此方法将返回 true。

Java 8 有一个重要的内置功能接口，就是[谓词](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)。谓词或条件检查函数，它检查给定条件的给定输入，并返回相同的布尔结果，指示条件是否满足。

**语法:**

```
public boolean removeIf(Predicate<? super E> filter)
```

**参数:**该方法采用参数**过滤器**，该过滤器代表一个谓词，该谓词为要移除的元素返回 true。

**返回:**如果谓词返回真且某些元素被移除，则此方法返回**真**。

**异常:**如果指定的过滤器为空，该方法抛出**空指针异常**。

下面的程序说明了向量的 removeIf()方法:

**例 1:** 在包含一组数字并且只有可被 2 整除的数字的向量上演示 removeIf()方法。

```
// Java Program Demonstrate removeIf()
// method of Vector

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an Vector which going to
        // contains a list of Numbers
        Vector<Integer> Numbers = new Vector<Integer>();

        // Add Number to list
        Numbers.add(22);
        Numbers.add(33);
        Numbers.add(55);
        Numbers.add(62);

        // apply removeIf() method
        // to remove numbers divisible by 2
        Numbers.removeIf(n -> (n % 2 == 0));

        System.out.println("All Numbers not divisible by 2 are:");

        // print list
        for (int i : Numbers) {
            System.out.println(i);
        }
    }
}
```

**输出:**

```
All Numbers not divisible by 2 are:
33
55

```

**示例 2:** 演示包含一组学生姓名的 Vector 上的 removeIf()方法，并删除所有 4 个字符长的姓名。

```
// Java Program Demonstrate removeIf()
// method of Vector

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Vector
        // containing a list of string values
        Vector<String> students = new Vector<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Rama");
        students.add("Mohan");
        students.add("Sohan");
        students.add("Rabi");
        students.add("Shabbir");

        // apply removeIf() method
        // to remove names contains 4 chars
        students.removeIf(n -> (n.length() == 4));

        System.out.println("Students name do not contain 4 char are");

        // print list
        for (String str : students) {
            System.out.println(str);
        }
    }
}
```

**输出:**

```
Students name do not contain 4 char are
Mohan
Sohan
Shabbir

```

**示例 3:** 演示 Vector 上 removeIf()方法中的 NullpointerException。

```
// Java Program Demonstrate removeIf()
// method of Vector

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Vector
        // containing a list of string values
        Vector<String> students = new Vector<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Rama");
        students.add("Mohan");
        students.add("Sohan");
        students.add("Rabi");
        students.add("Shabbir");

        try {
            // apply removeIf() method with null filter
            students.removeIf(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/vector . html # removeIf-Java . util . function . predicate-](https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html#removeIf-java.util.function.Predicate-)
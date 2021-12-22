# 什么是 Java 中的堆污染，如何解决？

> 原文:[https://www . geesforgeks . org/什么是 java 堆污染以及如何解决它/](https://www.geeksforgeeks.org/what-is-heap-pollution-in-java-and-how-to-resolve-it/)

<u>**什么是堆污染？**T3】</u>

堆污染意味着我们的[堆内存](https://www.geeksforgeeks.org/java-memory-management/)中有坏数据。在 Java 语言中，堆污染是当参数化类型的[变量](https://www.geeksforgeeks.org/variables-in-java/)指向非参数化类型的对象时发生的情况。

<u>**如何检测堆污染？**T3】</u>

通常，[编译器只在](https://www.geeksforgeeks.org/error-detection-recovery-compiler/) [**编译时**](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/) 检测到堆污染情况，并抛出未检查警告消息。

在运行时[](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/)**，有可能出现堆污染，从而导致**[class castexception](https://www.geeksforgeeks.org/built-exceptions-java-examples/)**。堆污染意味着堆内存中的坏数据。在这里，错误数据是一个类型为 X 的对象，但类型为 Y 的对象是预期的，它将在运行时引发 ClassCastException。**

****用程序了解堆污染:****

```
// Program to illustrate Heap pollution situation

import java.util.*;

class Geeks {
    public static void main(String[] args)
    {

        // Creating a List of type String
        List<String> listOfString = new ArrayList<>();
        listOfString.add("Geeksforgeeks");

        // Creating a List of type Integer which holds
        // the reference of a List of type String
        // Here compiler will detect that
        // there is a chance of Heap pollution
        // Compiler will throw an unchecked warning
        // at the compile-time only
        List<Integer> listOfInteger
            = (List<Integer>)(Object)listOfString;

        // Here we are trying to access
        // firstElement of listOfInteger which holds
        // the reference of a List of type String
        // and trying to store it into
        // one variable of type Integer
        Integer firstElement
            = listOfInteger.get(0);
        System.out.println(firstElement);
    }
}
```

****编译时控制台:****

```
prog.java:12: warning: [unchecked] unchecked cast
        List listOfInteger = (List)(Object)listOfString;
                                                     ^
  required: List
  found:    Object
1 warning 
```

****输出:****

> **线程“main”Java . lang . class castexception:Java . lang . string 无法在 Geeks.main(File.java:16)处强制转换为 java.lang.Integer**

**<u>**如何应对堆污？**T3】</u>**

```
// Program to illustrate Heap pollution with respect to varargs

import java.util.*;

class Geeks {
    public static void merge(List<String>... stringList)
    {
        // Here we are an array of type Object holds
        // reference of an array of type List<String>
        Object[] arr = stringList;
        List<Integer> temp = new ArrayList<Integer>();
        temp.add(420);

        // Here we are trying to assign temp
        // of type List<Integer> into arr[0]
        // which is of type List<String>

        // Here ClassCastException will be thrown
        arr[0] = temp;

        String firstEle = stringList[0].get(0);
        System.out.println(firstEle);
    }

    // Driver code
    public static void main(String args[])
    {
        List<String> list1 = new ArrayList<>();
        List<String> list2 = new ArrayList<>();
        List<String> list3 = new ArrayList<>();
        list1.add("Geeks");
        list2.add("for");
        list3.add("geeks");

        merge(list1, list2, list3);
    }
}
```

****编译时控制台:****

```
prog.java:4: warning:
 [unchecked] Possible heap pollution from
             parameterized vararg type List
    public static void merge(List... stringList)
                                             ^
prog.java:23: warning:
 [unchecked] unchecked generic array creation
             for varargs parameter of type List[]
        merge(list1, list2, list3);
             ^
2 warnings 
```

****输出:****

```
Exception in thread "main" java.lang.ClassCastException:
 java.lang.Integer cannot be cast to java.lang.String
    at Geeks.merge(File.java:10)
    at Geeks.main(File.java:23) 
```

****注意:**如果我们不想在编译时出现警告，那么我们可以在方法上面使用[@ safevarrags](https://www.geeksforgeeks.org/safevarargs-annotation-in-java-9-with-example/)注释。如果我们知道该方法不包含任何堆污染情况，那么您可以用@ SafeVarargs 注释它来抑制警告。这并不意味着它会允许我们的代码受到堆污染。这意味着如果在代码中有堆污染的可能，它会在运行时抛出 **ClassCastException** 。**

**<u>**如何防止堆污染情况？**T3】</u>**

**我们无法防止堆污染情况，但是我们可以遵循一些规则来帮助我们防止堆污染，例如:**

*   **不要对泛型类型使用 [varargs](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/) 参数，也不要将对象数组转换为泛型类型的数组。**
*   **不要将 [varargs](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/) 参数或泛型数组暴露给任何其他方法。**
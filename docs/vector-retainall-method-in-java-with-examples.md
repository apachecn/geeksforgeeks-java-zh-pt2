# Java 中的向量 retainAll()方法，示例

> 原文:[https://www . geesforgeks . org/vector-retain all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/vector-retainall-method-in-java-with-examples/)

java 中类[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)的**retainal**方法是 Java 中的一个内置函数，用于仅保留该向量中包含在指定集合中的元素。换句话说，从该向量中移除不包含在指定集合中的所有元素。

**语法:**

```
public boolean retainAll(Collection c)

```

**参数:**这里 **c** 是要保留在该向量中的元素的集合(所有其他元素都被移除)。

**返回值:**该方法将返回一个**布尔值**，即如果该向量因调用而改变则为真，否则为假。

**异常:**这个方法会抛出以下异常。

*   **class castexception–**如果该向量中一个或多个元素的类型与指定集合不兼容。*   **NullPointerException –**If this vector contains one or more null elements and the specified collection does not support null elements, or if the specified collection is null.

    下面的程序说明了 Java 中的 Vector.retainAll()方法:

    **程序 1:** 用 Java 说明 Vector.retainAll()方法。

    ```
    import java.util.*;
    import java.io.*;
    public class GFG {
        public static void main(String args[])
        {
            // Creating an empty Vector
            Vector<String> v1 = new Vector<String>();

            // adding elements to the vector v1
            v1.add("Geeks");
            v1.add("For");
            v1.add("Geeks");
            v1.add("is");
            v1.add("a");
            v1.add("computer");
            v1.add("science");
            v1.add("portal");

            System.out.println("Elements of vector1:" + v1);

            // Creating an other empty vector
            Vector<String> v2 = new Vector<String>();

            // adding elements to the vector v2
            v2.add("Geeks");
            v2.add("For");
            v2.add("Geeks");
            v2.add("contains");
            v2.add("well");
            v2.add("written");
            v2.add("programming");
            v2.add("articles");
            v2.add("and");
            v2.add("much");
            v2.add("more.");

            System.out.println("Elements of vector2:" + v2);

            System.out.println("Calling retainAll() method");
            // calling retainAll()
            v1.retainAll(v2);

            System.out.println("After calling retainAll() method");
            System.out.println(v1);
        }
    }
    ```

    **Output:**

    > vector1 的元素:[Geeks，For，Geeks，is，a，computer，science，portal]
    > vector 2 的元素:[Geeks，For，Geeks，包含，嗯，写的，编程，文章，等等。】
    > 调用 retail()方法
    > 调用 retail()方法
    > 后【极客，For，极客】

    **程序 2:** 用 Java 显示 retainAll()方法的返回值。

    ```
    import java.util.*;
    import java.io.*;

    public class GFG {
        public static void main(String args[])
        {

            // Creating an empty Vector
            Vector<String> v1 = new Vector<String>();

            // adding elements to the vector v1
            v1.add("Geeks");
            v1.add("For");
            v1.add("Geeks");
            v1.add("is");
            v1.add("a");
            v1.add("computer");
            v1.add("science");
            v1.add("portal");

            System.out.println("Elements of vector1:" + v1);

            // Creating an other empty vector
            Vector<String> v2 = new Vector<String>();

            // adding elements to the vector v2
            v2.add("Geeks");
            v2.add("For");
            v2.add("Geeks");
            v2.add("contains");
            v2.add("well");
            v2.add("written");
            v2.add("programming");
            v2.add("articles");
            v2.add("and");
            v2.add("many");
            v2.add("more.");

            System.out.println("Elements of vector1:" + v1);

            // calling retainAll()
            boolean t = v1.retainAll(v2);

            System.out.println("Calling retainAll() method: ");
            System.out.println(t);
        }
    }
    ```

    **Output:**

    > vector1 的元素:[Geeks，For，Geeks，is，a，计算机，科学，门户]
    > vector 1 的元素:[Geeks，For，Geeks，is，a，计算机，科学，门户]
    > 调用 retainAll()方法:
    > true
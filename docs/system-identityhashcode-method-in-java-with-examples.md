# Java 中的 System.identityHashCode()方法示例

> 原文:[https://www . geesforgeks . org/system-identity hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/system-identityhashcode-method-in-java-with-examples/)

Java . lang . system . identity HashCode()是用于为任何给定对象返回相同哈希代码的方法，该哈希代码由默认方法 hashCode()返回。此外，对于每个具有空引用的哈希代码，都会返回零。

**需要记住的点:**

*   默认情况下，每个类都隐式或显式地提供一个 hashCode()方法
*   hashcode 通常是从任何对象生成的数字，它允许对象在 Hashtable 中非常快速地存储或检索。
*   在 Java 中，hashCode()默认情况下是一个本机方法，这意味着该方法有一个修饰符“native”，当它直接在 JVM 中的本机代码中实现时。
*   Used to digest all the data stored in an instance of the class into a single hash value i.e., a 32-bit signed integer.

    **语法:**

    ```java
    public static int identityHashCode(Object x)
    ```

    **参数:**参数 *x* 属于哈希类型，是指需要计算的哈希码。

    **返回值:**这个方法返回 hashCode。

    下面的程序说明了 Java . lang . system . identity hashcode()方法的使用。

    **程序 1:**

    ```java
    // Java program to demonstrate working
    // of java.lang.System.identityHashCode() method.
    import java.lang.*;
    import java.io.*;

    public class SystemCode1 {

        public static void main(String[] args) throws Exception
        {

            File filename1 = new File("Welcome");
            File filename2 = new File("Welcome");
            File filename3 = new File("Geek");
            File filename4 = new File("World");

            // Returns the HashCode
            int returnvalue1 = System.identityHashCode(filename1);
            System.out.println(returnvalue1);

            // Returns different HashCode for same filename
            int returnvalue2 = System.identityHashCode(filename2);
            System.out.println(returnvalue2);

            // Returns the HashCode
            int returnvalue3 = System.identityHashCode(filename3);
            System.out.println(returnvalue3);

            // Returns the HashCode
            int returnvalue4 = System.identityHashCode(filename4);
            System.out.println(returnvalue4);
        }
    }
    ```

    **Output:**

    ```java
    589431969
    1252169911
    2101973421
    685325104

    ```

    **说明:**
    在上面的程序中，不同的 hashcode 或 number 是从一个对象生成的，即使它们有相同的名称。像这里一样，我们可以看到前两个术语是相同的，即“欢迎”，但是我们有两个不同的值，它们是

    *   Five hundred and eighty-nine million four hundred and thirty-one thousand nine hundred and sixty-nine
    *   One billion two hundred and fifty-two million one hundred and sixty-nine thousand nine hundred and eleven

    分别为第一和第二**欢迎**

    **程序 2:**

    ```java
    // Java program to demonstrate working
    // of java.lang.System.identityHashCode() method.
    import java.lang.*;
    import java.io.*;

    public class SystemCode2 {

        public static void main(String[] args) throws Exception
        {

            File filename1 = new File("10");
            File filename2 = new File("shyam");
            File filename3 = new File("s12");
            File filename4 = new File("s12");

            // Returns the HashCode
            int returnvalue1 = System.identityHashCode(filename1);
            System.out.println(returnvalue1);

            // Returns the HashCode
            int returnvalue2 = System.identityHashCode(filename2);
            System.out.println(returnvalue2);

            // Returns different HashCode for same filename
            int returnvalue3 = System.identityHashCode(filename3);
            System.out.println(returnvalue3);

            // Returns different HashCode for same filename
            int returnvalue4 = System.identityHashCode(filename4);
            System.out.println(returnvalue4);
        }
    }
    ```

    **Output:**

    ```java
    589431969
    1252169911
    2101973421
    685325104

    ```
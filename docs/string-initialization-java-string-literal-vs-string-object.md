# 字符串文字 Vs Java 中的字符串对象

> 原文:[https://www . geesforgeks . org/string-initialization-Java-string-literal-vs-string-object/](https://www.geeksforgeeks.org/string-initialization-java-string-literal-vs-string-object/)

比较字符串文字和字符串对象的字符串初始化性能。
**字符串文字**

> str 字符串= " geeksforgeeks

这是字符串。当您像这样声明字符串时，实际上是在字符串上调用 intern()方法。此方法**引用字符串对象的内部池**。如果已经存在一个字符串值“极客”，那么字符串将引用该字符串，并且不会创建新的字符串对象。详见[Java 中的初始化和比较字符串](https://www.geeksforgeeks.org/how-to-initialize-and-compare-strings-in-java/)。

**字符串对象**

> String str = new String(" geeksforgeks ")；

这是字符串对象。在这种方法中，JVM 被迫创建一个新的字符串引用，即使“GeeksForGeeks”在引用池中。

因此，如果我们比较字符串文字和字符串对象的性能，字符串对象将总是比字符串文字花费更多的时间来执行，因为它将在每次执行时构造一个新的字符串。
**注意:**执行时间取决于编译器。

下面是比较它们性能的 Java 程序。

```
// Java program to compare performance 
// of string literal and string object

class ComparePerformance {

    public static void main(String args[])
    {    
        // Initialization time for String
        // Literal
        long start1 = System.currentTimeMillis();

        for (int i = 0; i < 10000; i++)
        {
            String s1 = "GeeksForGeeks";
            String s2 = "Welcome";
        }

        long end1 = System.currentTimeMillis();
        long total_time = end1 - start1;

        System.out.println("Time taken to execute"+ 
                " string literal = " + total_time);

        // Initialization time for String
        // object
        long start2 = System.currentTimeMillis();

        for (int i = 0; i < 10000; i++)
        {
            String s3 = new String("GeeksForGeeks");
            String s4 = new String("Welcome");
        }

        long end2 = System.currentTimeMillis();
        long total_time1 = end2 - start2;

        System.out.println("Time taken to execute"+
                   " string object=" + total_time1);
    }
}
```

**输出:**

```
Time taken to execute string literal = 0
Time taken to execute string object = 2

```
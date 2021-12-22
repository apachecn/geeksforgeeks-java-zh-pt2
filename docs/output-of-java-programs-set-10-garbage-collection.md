# Java 程序输出|第 10 集(垃圾收集)

> 原文:[https://www . geesforgeks . org/output-of-Java-programs-set-10-垃圾收集/](https://www.geeksforgeeks.org/output-of-java-programs-set-10-garbage-collection/)

先决条件–[Java 中的垃圾收集](https://www.geeksforgeeks.org/garbage-collection-java/)

**难度等级:**中级
在 Java 中，对象销毁由[垃圾收集器](https://www.geeksforgeeks.org/garbage-collection-java/)模块负责，没有任何引用的对象都有资格进行垃圾收集。下面是一些关于垃圾收集的重要输出问题。
预测以下 Java 程序的输出:

*   **Program 1 :**

    ```
    public class Test
    {
        public static void main(String[] args) throws InterruptedException
        {
            String str = new String("GeeksForGeeks");

            // making str eligible for gc
            str = null; 

            // calling garbage collector
            System.gc(); 

            // waiting for gc to complete
            Thread.sleep(1000); 

            System.out.println("end of main");
        }

        @Override
        protected void finalize() 
        {
            System.out.println("finalize method called");
        }
    }
    ```

    输出:

    ```
    end of main

    ```

    **说明:**我们知道 [finalize()](https://www.geeksforgeeks.org/g-fact-24-finalfinally-and-finalize-in-java/) 方法是垃圾收集器在销毁一个对象之前对其调用的。但是在这里，技巧是字符串是字符串类对象，而不是测试类。因此，在字符串上调用字符串类的 finalize()方法(如果在字符串类中被重写)。如果一个类没有覆盖 finalize 方法，那么默认情况下调用 Object 类 finalize()方法。

*   **程序 2 :**

```
public class Test
{
    public static void main(String[] args) throws InterruptedException
    {
        Test t = new Test();

        // making t eligible for garbage collection
        t = null; 

        // calling garbage collector
        System.gc(); 

        // waiting for gc to complete
        Thread.sleep(1000); 

        System.out.println("end main");
    }

    @Override
    protected void finalize() 
    {
        System.out.println("finalize method called");
        System.out.println(10/0);
    }

}
```

输出:

```
finalize method called
end main

```

**解释:**
当垃圾收集器对一个对象调用 finalize()方法时，**忽略**该方法中引发的所有异常，程序将正常终止。

*   **Program 3 :**

    ```
    public class Test
    {
        static Test t ;

        static int count =0;

        public static void main(String[] args) throws InterruptedException
        {
            Test t1 = new Test();

            // making t1 eligible for garbage collection
            t1 = null; // line 12

            // calling garbage collector
            System.gc(); // line 15

            // waiting for gc to complete
            Thread.sleep(1000); 

            // making t eligible for garbage collection,
            t = null; // line 21

            // calling garbage collector
            System.gc(); // line 24

            // waiting for gc to complete
            Thread.sleep(1000); 

            System.out.println("finalize method called "+count+" times");

        }

        @Override
        protected void finalize() 
        { 
            count++;

            t = this; // line 38

        }

    }
    ```

    **输出:**

    ```
    finalize method called 1 times

    ```

    **说明:**
    12 号线执行后，T1 具备垃圾收集资格。因此，当我们在第 15 行调用垃圾收集器时，垃圾收集器将在 t1 上调用 finalize()方法，然后销毁它。但是在 finalize 方法中，在第 38 行，我们再次通过 t 引用同一个对象，所以在执行第 38 行之后，[这个](https://www.geeksforgeeks.org/this-reference-in-java/)对象不再有资格进行垃圾收集。因此，垃圾收集器不会销毁对象。

    现在，在第 21 行中，我们再次让同一个对象有资格进行垃圾收集。在这里，我们必须弄清楚一个关于垃圾收集器的事实，即它将在一个特定的对象上精确地调用 finalize()方法**一次**。因为在这个对象上已经调用了 finalize()方法，所以现在垃圾收集器将销毁它，而不会再次调用 finalize()方法。

    *   **Program 4 :**

    ```
    public class Test
    {
        public static void main(String[] args)
        {
            // How many objects are eligible for 
            // garbage collection after this line?
            m1();  // Line 5
        }

        static void m1() 
        {
            Test t1 = new Test();
            Test t2 = new Test();
        } 
    }
    ```

    **问题:**
    5 号线执行后有多少对象符合垃圾回收条件？
    T4【回答:

    ```
    2

    ```

    **解释:**
    由于 T1 和 T2 是 m1()方法的本地对象，因此它们在方法完全执行后就有资格进行垃圾收集，除非返回其中任何一个。

    *   **Program 5 :**

    ```
    public class Test
    {
        public static void main(String [] args) 
        {
            Test t1 = new Test();
            Test t2 = m1(t1); // line 6
            Test t3 = new Test();
            t2 = t3; // line 8

        }

        static Test m1(Test temp) 
        {
            temp = new Test();
            return temp;
        }
    }
    ```

    **问题:**
    8 号线执行后有多少对象符合垃圾回收条件？
    T4【回答:

    ```
    1

    ```

    **解释:**
    到第 8 行执行时，唯一没有引用的对象是第 6 行生成的对象。记住“ [Java 是严格按值传递的](https://www.geeksforgeeks.org/passing-and-returning-objects-in-java/)”，所以引用变量 t1 不受 m1()方法的影响。我们可以使用 finalize()方法来检查它。finalize()方法中的语句“system . out . println(this . hashcode())”打印调用 finalize()方法的对象 hashcode 值，然后只需将该值与 main 方法中创建的其他对象 hashcode 值进行比较。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
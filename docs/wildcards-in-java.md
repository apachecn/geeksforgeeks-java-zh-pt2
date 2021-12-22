# Java 中的通配符

> 原文:[https://www.geeksforgeeks.org/wildcards-in-java/](https://www.geeksforgeeks.org/wildcards-in-java/)

问号(？)被称为泛型编程中的通配符。它代表未知类型。通配符可用于各种情况，如参数、字段或局部变量的类型；有时作为返回类型。与数组不同，泛型类型的不同实例化彼此不兼容，甚至不显式兼容。这种不兼容性可以通过通配符来缓和，如果？用作实际类型参数。

**Java 中通配符的类型:**

1.  **Upper Bounded Wildcards:** These wildcards can be used when you want to relax the restrictions on a variable. For example, say you want to write a method that works on List < integer >, List < double >, and List < number > , you can do this  using an upper bounded wildcard.
    To declare an upper-bounded wildcard, use the wildcard character (‘?’), followed by the extends keyword, followed by its upper bound.

    ```java
    public static void add(List<? extends Number> list)
    ```

    **实施:**

    ```java
    //Java program to demonstrate Upper Bounded Wildcards
    import java.util.Arrays;
    import java.util.List;

    class WildcardDemo
    {
        public static void main(String[] args)
        {

            //Upper Bounded Integer List
            List<Integer> list1= Arrays.asList(4,5,6,7);

            //printing the sum of elements in list
            System.out.println("Total sum is:"+sum(list1));

            //Double list
            List<Double> list2=Arrays.asList(4.1,5.1,6.1);

            //printing the sum of elements in list
            System.out.print("Total sum is:"+sum(list2));
        }

        private static double sum(List<? extends Number> list) 
        {
            double sum=0.0;
            for (Number i: list)
            {
                sum+=i.doubleValue();
            }

            return sum;
        }
    }
    ```

    **输出:**

    ```java
    Total sum is:22.0
    Total sum is:15.299999999999999
    ```

    在上面的程序中，list1 和 list2 是 list 类的对象。list1 是 Integer 的集合，list2 是 Double 的集合。它们都被传递给方法 sum，该方法有一个扩展 Number 的通配符。这意味着被传递的列表可以是任何字段或该字段的子类。这里，整数和双精度是类 Number 的子类。

2.  **Lower Bounded Wildcards:** It is expressed using the wildcard character (‘?’), followed by the super keyword, followed by its lower bound: <? super A>.

    ```java
     Syntax: Collectiontype <? super A>
    ```

    **执行:** 

    ```java
    //Java program to demonstrate Lower Bounded Wildcards
    import java.util.Arrays;
    import java.util.List;

    class WildcardDemo
    {
        public static void main(String[] args)
        {
            //Lower Bounded Integer List
            List<Integer> list1= Arrays.asList(4,5,6,7);

            //Integer list object is being passed
            printOnlyIntegerClassorSuperClass(list1);

            //Number list
            List<Number> list2= Arrays.asList(4,5,6,7);

            //Integer list object is being passed
            printOnlyIntegerClassorSuperClass(list2);
        }

        public static void printOnlyIntegerClassorSuperClass(List<? super Integer> list)
        {
            System.out.println(list);
        }
    }
    ```

    **输出:**

    ```java
    [4, 5, 6, 7]
    [4, 5, 6, 7]
    ```

    这里的参数可以是整数或整数的超类(即数字)。printlonlineintegerclassor super class 方法将只接受整数或其超类对象。然而，如果我们传递类型为 Double 的列表，那么我们将得到编译错误。这是因为只能传递整数字段或其超类。Double 不是整数的超类。

    当您想要从结构中获取值时，请使用扩展通配符，当您将值放入结构中时，请使用超级通配符。在结构中获取和放置值时，不要使用通配符。

    注意:您可以指定通配符的上限，也可以指定下限，但不能同时指定两者。

3.  **Unbounded Wildcard:** This wildcard type is specified using the wildcard character (?), for example, List. This is called a list of unknown type. These are useful in the following cases
    *   当编写可以使用对象类中提供的功能的方法时。
    *   当代码使用泛型类中不依赖于类型参数的方法时

    **执行:** 

    ```java
    //Java program to demonstrate Unbounded wildcard
    import java.util.Arrays;
    import java.util.List;

    class unboundedwildcardemo
    {
        public static void main(String[] args) 
        {

            //Integer List
            List<Integer> list1= Arrays.asList(1,2,3);

            //Double list
            List<Double> list2=Arrays.asList(1.1,2.2,3.3);

            printlist(list1);

            printlist(list2);
        }

        private static void printlist(List<?> list) 
        {

            System.out.println(list);
        }
    }
    ```

    输出:

    ```java
    [1, 2, 3]
    [1.1, 2.2, 3.3]
    ```

    本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
# 在 Java 中返回多个值

> 原文:[https://www . geesforgeks . org/returning-multi-values-in-Java/](https://www.geeksforgeeks.org/returning-multiple-values-in-java/)

Java 不支持多值返回。我们可以使用以下解决方案来返回多个值。

**如果所有返回的元素都是同一类型**

我们可以用 Java 返回一个数组。下面是一个 Java 程序来演示同样的情况。

```
// A Java program to demonstrate that a method
// can return multiple values of same type by
// returning an array
class Test {
    // Returns an array such that first element
    // of array is a+b, and second element is a-b
    static int[] getSumAndSub(int a, int b)
    {
        int[] ans = new int[2];
        ans[0] = a + b;
        ans[1] = a - b;

        // returning array of elements
        return ans;
    }

    // Driver method
    public static void main(String[] args)
    {
        int[] ans = getSumAndSub(100, 50);
        System.out.println("Sum = " + ans[0]);
        System.out.println("Sub = " + ans[1]);
    }
}
```

**Output:**

```
Sum = 150
Sub = 50

```

**如果返回的元素是不同类型的**

**使用 Pair(如果只有两个返回值)**
我们可以使用 Java 中的[Pair](https://www.geeksforgeeks.org/pair-class-in-java/)返回两个值。

```
// Returning a pair of values from a function
import javafx.util.Pair;

class GfG {
    public static Pair<Integer, String> getTwo()
    {
        return new Pair<Integer, String>(10, "GeeksforGeeks");
    }

    // Return multiple values from a method in Java 8
    public static void main(String[] args)
    {
        Pair<Integer, String> p = getTwo();
        System.out.println(p.getKey() + " " + p.getValue());
    }
}
```

**如果返回值超过两个**
我们可以将所有返回的类型封装到一个类中，然后返回该类的一个对象。

让我们看看下面的代码。

```
// A Java program to demonstrate that we can return
// multiple values of different types by making a class
// and returning an object of class.

// A class that is used to store and return
// three members of different types
class MultiDivAdd {
    int mul; // To store multiplication
    double div; // To store division
    int add; // To store addition
    MultiDivAdd(int m, double d, int a)
    {
        mul = m;
        div = d;
        add = a;
    }
}

class Test {
    static MultiDivAdd getMultDivAdd(int a, int b)
    {
        // Returning multiple values of different
        // types by returning an object
        return new MultiDivAdd(a * b, (double)a / b, (a + b));
    }

    // Driver code
    public static void main(String[] args)
    {
        MultiDivAdd ans = getMultDivAdd(10, 20);
        System.out.println("Multiplication = " + ans.mul);
        System.out.println("Division = " + ans.div);
        System.out.println("Addition = " + ans.add);
    }
}
```

**Output:**

```
Multiplication = 200
Division = 0.5
Addition = 30

```

**返回[对象类列表](https://www.geeksforgeeks.org/object-class-in-java/)**

```
// Java program to demonstrate return of
// multiple values from a function using
// list Object class.
import java.util.*;

class GfG {
    public static List<Object> getDetails()
    {
        String name = "Geek";
        int age = 35;
        char gender = 'M';

        return Arrays.asList(name, age, gender);
    }

    // Driver code
    public static void main(String[] args)
    {
        List<Object> person = getDetails();
        System.out.println(person);
    }
}
```

**Output:**

```
[Geek, 35, M]

```

本文由**闪烁泰亚吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论
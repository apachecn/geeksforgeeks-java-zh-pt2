# Java 中的变量参数(Varargs)

> 原文:[https://www . geesforgeks . org/variable-args-in-Java/](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/)

Java 中的变量参数(Varargs)是一种接受可变数量参数的方法。Java 中的可变参数简化了需要接受可变数量参数的方法的创建。

### 需要 Java 变量

*   在 JDK 4 之前，我们不能声明一个带有可变参数个数的方法。如果参数的数量有任何变化，我们必须声明一个新的方法。这种方法增加了代码的长度，降低了可读性。
*   在 JDK 5 之前，可变长度参数有两种处理方式。一个使用重载方法(每个方法一个)，另一个将参数放入数组，然后将该数组传递给方法。两者都有潜在的错误倾向，需要更多的代码。
*   为了解决这些问题，在 JDK 5 中引入了可变参数。从 JDK 5 开始，我们可以用可变数量的参数来声明一个方法。这种类型的方法称为 Varargs 方法。varargs 特性提供了一个更简单、更好的选项。

**Varargs 的语法**

在内部，Varargs 方法通过使用一维数组的概念来实现。因此，在 Varrargs 方法中，我们可以使用索引来区分参数。可变长度参数由三个句点或点(…)指定。

***例如***

```
public static void fun(int ... a) 
{
   // method body
} 
```

该语法告诉编译器 fun()可以用零个或多个参数调用。因此，在这里，被隐式声明为 int[]类型的数组。

以下是用于说明上述概念的代码片段:

## Java

```
// Java program to demonstrate varargs

class Test1 {
    // A method that takes variable
    // number of integer arguments.
    static void fun(int... a)
    {
        System.out.println("Number of arguments: "
                           + a.length);

        // using for each loop to display contents of a
        for (int i : a)
            System.out.print(i + " ");
        System.out.println();
    }

    // Driver code
    public static void main(String args[])
    {
        // Calling the varargs method with
        // different number of parameters

        // one parameter
        fun(100);

          // four parameters
        fun(1, 2, 3, 4);

          // no parameter
          fun();
    }
}
```

**Output**

```
Number of arguments: 1
100 
Number of arguments: 4
1 2 3 4 
Number of arguments: 0
```

**解释上述程序的**

*   **…… the syntax tells the compiler that varargs has been used, and these parameters should be stored in the referenced **array.****
***   The variable **a** operates as an array. In this case, we define the data type of array "a" as int. So only integer values can be taken. The number of parameters can be calculated by a.length, which is our method of calculating array length in Java.**

****注意:**一个方法也可以有可变长度的参数和其他参数，但是应该确保只有一个 varargs 参数应该写在方法声明的参数列表的最后。例如:**

```
int nums(int a, float b, double … c)
```

**在这种情况下，前两个参数与前两个参数匹配，其余参数属于 c .**

## **Java**

```
// Java program to demonstrate
//  varargs with normal arguments

class Test2 {

    // Takes string as a argument followed by varargs
    static void fun2(String str, int... a)
    {
        System.out.println("String: " + str);
        System.out.println("Number of arguments is: "
                           + a.length);

        // using for each loop to display contents of a
        for (int i : a)
            System.out.print(i + " ");

        System.out.println();
    }

    public static void main(String args[])
    {
        // Calling fun2() with different parameter
        fun2("GeeksforGeeks", 100, 200);
        fun2("CSPortal", 1, 2, 3, 4, 5);
        fun2("forGeeks");
    }
}
```

****Output**

```
String: GeeksforGeeks
Number of arguments is: 2
100 200 
String: CSPortal
Number of arguments is: 5
1 2 3 4 5 
String: forGeeks
Number of arguments is: 0
```** 

### **错误的 Varargs 示例**

****案例 1:** 在一个方法中指定两个变量:**

```
void method(String... gfg, int... q)
{
    // Compile time error as there 
    // are two varargs
}
```

****情况 2:** 指定 Varargs 作为方法的第一个参数，而不是最后一个参数:**

```
void method(int... gfg, String q)
{
    // Compile time error as vararg 
    // appear before normal argument
}
```

### **关于 Varargs 的要点**

*   **Vararg 方法也可以重载，但是重载可能会导致歧义。**
*   **在 JDK 5 之前，可变长度参数有两种处理方式:一种是使用重载，另一种是使用数组参数。**
*   **一个方法中只能有一个变量参数。**
*   **变量参数(Varargs)必须是最后一个参数。**

**本文由 **Niraj Srimal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇关于[write.geeksforgeeks.org](https://write.geeksforgeeks.org/)的文章。看到你的文章出现在极客博客主页上，帮助其他极客。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论**
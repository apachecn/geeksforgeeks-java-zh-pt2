# 【Java 和 C++的相似之处

> 原文:[https://www . geesforgeks . org/相似点-介于-java 和-c/](https://www.geeksforgeeks.org/similarities-between-java-and-c/)

两者都是非常成功和流行的编程语言。尽管两者之间有许多不同之处，但也有许多相似之处，如下所示:

1.  **Both C++ and Java supports Object Oriented Programming:**

    OOPs 是一种模块化的方法，它允许在规定的程序区域内应用数据，它还提供了可重用的特性来开发生产逻辑，这意味着更加重视数据。它支持类和对象。OOPs 功能包括:

    *   **继承:**一个类的对象可以链接和共享另一个类的对象的一些公共属性的过程。

    *   **多态性:**允许我们以不同的方式执行单个动作。它是将一个函数用于多个目的的过程。

    *   **抽象:**是在不包含背景细节的情况下表现本质特征的行为。

    *   **封装。:**将数据和功能打包成一个单元。

2.  **They have similar syntax:**

    **C++语法:**

    ```java
    #include& lt; iostream & gt;
    using namespace std;

    int main()
    {
        cout& lt;
        <
        "
        Hello World"
        ;
        return 0;
    }
    ```

    **Java 语法:**

    ```java
    public class first {
        public static void main(String[] args)
        {
            // prints Hello World
            System.out.println(" Hello World ");
        }
    }
    ```

3.  **Comments Syntax are identical**:

    单行和多行注释都写成//…。和/* …。*/分别为。

    **C++:**

    ```java
    #include <iostream>
    using namespace std;

    int main()
    { // main() is where program execution begins
        int a = 5, b = 10, sum;
        sum = a + b;

        /* This will add the values of a and b
    and will display the output stored in sum */

        cout << sum;
        return 0;
    }
    ```

    **Java:**

    ```java
    public class GFG {

        public static void main(String[] args)
        { // main() is where program execution begins

            int a = 5, b = 10, sum;
            sum = a + b;

            /* This will add the values of a and b
    and will display the output stored in sum */

            System.out.println(sum);
        }
    }
    ```

4.  **The loops (like while, for etc.) and conditional statements (like if-else, switch etc.) are similar**:

    **C++:**

    ```java
    #include <iostream>
    using namespace std;

    int main()
    {
        int a = 5, b = 10;
        if (a > b)
            cout << a;

        else
            cout << b;
        return 0;
    }
    ```

    ```java
    Output: 10
    ```

    **Java:**

    ```java
    public class firstjava {

        public static void main(String[] args)
        {
            // to display the greater number

            int a = 5, b = 10;
            if (a > b)
                System.out.println(a);

            else
                System.out.println(b);
        }
    }
    ```

    ```java
    Output: 10
    ```

5.  **Both have same arithmetic and relational operators.**

    ```java
    Arithmetic operators such as +, -, *, /
    Relational operators such as >, <, =, != (not equal to)

    ```

6.  **Execution of both the C++ and Java programs starts from the main function:**
    It is the entry point of the execution of the program. However, the function declaration is different, but the name is same.

    **C++:**

    ```java
    #include& lt; iostream & gt;
    using namespace std;

    int main()
    { // main() is where program execution begins
        cout& lt;
        <
        "
        Hello World"
        ;
        return 0;
    }
    ```

    **Java:**

    ```java
    public class GFG {
        public static void main(String[] args)
        {
            // main() is where program execution begins
            System.out.println(" Hello World ");
        }
    }
    ```

7.  **它们具有相同的原始数据类型** :
    这些数据类型包括 int、float、char、double 等。有一些区别，比如布尔数据类型在 Java 中被称为布尔，但在 C++中被称为 bool。

8.  **Many of their keywords are same**:
    Example:

    ```java
    break, continue, char, double, new, public, private, return, static etc. 
    ```

9.  **都有多线程支持** :
    都允许同时执行多个线程(子进程)，实现多任务处理。

10.  **应用领域** :
    C++最适合开发大型软件，如图书馆管理系统、员工管理系统、乘客预订系统等。
    Java 可以用来开发所有这些软件，但除此之外，Java 最适合开发通信/互联网应用软件。例如:网络协议、互联网程序、网页、网络浏览器等。

**[学习 Java](https://www.geeksforgeeks.org/java/)**
**[学习 C++](https://www.geeksforgeeks.org/c-plus-plus/)**
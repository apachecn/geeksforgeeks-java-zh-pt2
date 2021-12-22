# Java 中的递归

> 原文:[https://www.geeksforgeeks.org/recursion-in-java/](https://www.geeksforgeeks.org/recursion-in-java/)

**什么是递归？**
函数直接或间接调用自身的过程称为递归，相应的函数称为递归函数。使用递归算法，某些问题可以很容易地解决。此类问题的例子有河内(TOH)[塔、](https://www.geeksforgeeks.org/c-program-for-tower-of-hanoi/)[有序/前序/后序树遍历](https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/)、[图的 DFS](https://www.geeksforgeeks.org/depth-first-traversal-for-a-graph/)等。

**递归中的基条件是什么？**
在递归程序中，提供基本情况的解，较大问题的解用较小的问题表示。

```
int fact(int n)
{
    if (n < = 1) // base case
        return 1;
    else    
        return n*fact(n-1);    
}

```

在上面的例子中，定义了 n < = 1 的基本情况，并且可以通过转换成较小的数值直到达到基本情况来解决较大的数值。

**如何使用递归解决特定问题？**
这个想法是用一个或多个较小的问题来表示一个问题，并添加一个或多个停止递归的基本条件。例如，如果我们知道(n-1)的阶乘，我们就计算阶乘 n。阶乘的基本情况是 n = 0。当 n = 0 时，我们返回 1。

**递归中为什么会出现堆栈溢出错误？**
如果没有达到或者没有定义基本情况，那么可能会出现栈溢出问题。让我们举个例子来理解这一点。

```
int fact(int n)
{
    // wrong base case (it may cause
    // stack overflow).
    if (n == 100) 
        return 1;

    else
        return n*fact(n-1);
}

```

如果调用 fact(10)，它会调用 fact(9)、fact(8)、fact(7)等等，但这个数字永远不会达到 100。所以，基本情况是达不到的。如果堆栈上的这些函数耗尽了内存，将导致堆栈溢出错误。

**直接递归和间接递归有什么区别？**
一个函数 fun 如果调用同一个函数 fun，叫做直接递归。如果函数 fun 调用另一个函数，比如 fun_new，fun_new 直接或间接调用 fun，那么这个函数叫做间接递归。表 1 说明了直接递归和间接递归的区别。

*   **直接递归:**

    ```
    void directRecFun()
    {
        // Some code....

        directRecFun();

        // Some code...
    }

    ```

*   **间接递归:**

    ```
    void indirectRecFun1()
    {
        // Some code...

        indirectRecFun2();

        // Some code...
    }

    void indirectRecFun2()
    {
        // Some code...

        indirectRecFun1();

        // Some code...
    }

    ```

**有尾递归和无尾递归有什么区别？**
当递归调用是函数执行的最后一件事时，递归函数是尾部递归。详见[尾部递归篇](https://www.geeksforgeeks.org/tail-recursion/)。

**递归中不同的函数调用是如何分配内存的？**
当从 main()调用任何函数时，内存会在堆栈上分配给它。递归函数调用自己，被调用函数的内存分配在分配给调用函数的内存之上，并且为每个函数调用创建不同的局部变量副本。当达到基本情况时，函数将其值返回给调用它的函数，内存被取消分配，过程继续。

让我们以一个简单的函数来举例说明递归是如何工作的。

```
// A Java program to demonstrate
// working of recursion

class GFG {
    static void printFun(int test)
    {
        if (test < 1)
            return;

        else {
            System.out.printf("%d ", test);

            // Statement 2
            printFun(test - 1);

            System.out.printf("%d ", test);
            return;
        }
    }

    public static void main(String[] args)
    {
        int test = 3;
        printFun(test);
    }
}
```

**Output:**

```
3 2 1 1 2 3

```

当从 main()调用 **printFun(3)** 时，内存被分配给 **printFun(3)** ，一个局部变量测试被初始化为 3，语句 1 到 4 被推送到堆栈上，如下图所示。它首先打印“3”。在语句 2 中，调用 **printFun(2)** 并将内存分配给 **printFun(2)** ，并将局部变量测试初始化为 2，并将语句 1 至 4 推入堆栈。同样的， **printFun(2)** 调用**print fun(1)****print fun(1)**调用 **printFun(0)** 。 **printFun(0)** 转到 if 语句，返回 **printFun(1)** 。执行 **printFun(1)** 的剩余语句，返回 **printFun(2)** 以此类推。在输出中，打印从 3 到 1 的值，然后打印 1 到 3。内存堆栈如下图所示。

![recursion](img/ea5c874dcd478216570adf2edbd3041e.png)

**递归编程相对于迭代编程有哪些缺点？**
注意递归和迭代程序都有相同的解题能力，即每个递归程序都可以迭代编写，反之亦然。递归程序比迭代程序有更大的空间需求，因为所有函数都将保留在堆栈中，直到达到基本情况。由于函数调用和返回开销，它也有更大的时间要求。

**递归编程相比迭代编程有哪些优势？**
递归提供了一种简洁明了的代码编写方式。有些问题本质上是递归的，比如树遍历、[汉诺塔](https://www.geeksforgeeks.org/c-program-for-tower-of-hanoi/)等。对于此类问题，最好编写递归代码。借助堆栈数据结构，我们也可以迭代地编写这样的代码。例如参考[无递归有序树遍历](https://www.geeksforgeeks.org/inorder-tree-traversal-without-recursion/)、[河内迭代塔](https://www.geeksforgeeks.org/iterative-tower-of-hanoi/)。
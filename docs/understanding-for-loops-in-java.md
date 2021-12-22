# 理解 Java 中的循环

> 原文:[https://www . geeksforgeeks . org/了解-for-loops-in-java/](https://www.geeksforgeeks.org/understanding-for-loops-in-java/)

假设需要打印从 1 到 5 的数字。一种可能的方法是借助下面的代码:

```
class GFG {
    public static void main(String args[])
    {

        int a;
        a = 1;
        System.out.println(a);
        a=2;
        System.out.println(a);
        a=3;
        System.out.println(a);
        a=4;
        System.out.println(a);
        a=5;
        System.out.println(a);
    }
}
```

上面的代码看起来可能很简单，但它有很多缺点，例如:

*   **固定代码:**该代码仅打印数字 1 至 5。如果需要一些其他数字或其他模式呢？在这种情况下，该解决方案将建议用新的所需值编写另一个程序，或者更改现有程序中的每个单独值。这种情况会一直持续下去，导致一个长而固定的结构被多次写入。
*   **重复代码:**如最后一点所述，这个解决方案建议用修改后的值重新编写整个程序，或者每次修改现有程序中的值。但是如果需要 100 个这样的模式呢。这将导致大量重复和不必要的代码。
*   **未概括:**建议的解决方案未概括。这意味着要打印的数字由用户静态地输入到代码中。没有预定义的模式，代码遵循该模式并根据该模式打印代码。
*   **不可伸缩:**计算机科学中编写的每一个代码都必须以可伸缩的方式编写。这意味着代码必须以最少的更改次数正常运行，才能打印数字 1 到 100。

每当需要重复一个过程时，“循环”就来了。

### [什么是循环？](https://www.geeksforgeeks.org/loops-in-java/)

编程语言中的循环是一种功能，当某些条件评估为真时，它有助于重复执行一组指令/函数。
Java 提供了三种执行循环的方式。虽然所有的方法都提供类似的基本功能，但是它们的语法和条件检查时间不同。

1.  **while loop:** A while loop is a control flow statement that allows code to be executed repeatedly based on a given Boolean condition. The while loop can be thought of as a repeating if statement.
    **Syntax :**

    ```
    while (boolean condition)
    {
       loop statements...
    }

    ```

    流程图:
    [![while loop](img/768d1cc1c0fcb376b6c69dd07663873b.png)](https://media.geeksforgeeks.org/wp-content/uploads/Loop1.png)

2.  **for loop:** for loop provides a concise way of writing the loop structure. Unlike a while loop, a for statement consumes the initialization, condition and increment/decrement in one line thereby providing a shorter, easy to debug structure of looping.
    **Syntax:**

    ```
    for (initialization condition; testing condition; 
                                  increment/decrement)
    {
        statement(s)
    }

    ```

    流程图:
    ![for-loop-in-java](img/a61667f20ad5f2b2fdadab840a64fdf9.png)

    **增强 For 循环**

    Java 还包括 Java 5 中引入的 for 循环的另一个版本。增强的 for 循环提供了一种更简单的方法来迭代集合或数组的元素。它是不灵活的，应该仅在需要以顺序方式迭代元素而不知道当前处理的元素的索引时使用。
    **语法:**

    ```
    for (T element:Collection obj/array)
    {
        statement(s)
    }

    ```

3.  **do while:** do while loop is similar to while loop with only difference that it checks for condition after executing the statements, and therefore is an example of **Exit Control Loop.**
    **Syntax:**

    ```
    do
    {
        statements..
    }
    while (condition);

    ```

    流程图:
    [![do-while](img/c8ed474a00731a50269426e7b2fca021.png)](https://media.geeksforgeeks.org/wp-content/uploads/loop3.png)

    ### 怎么写循环？

    仔细观察上面给出的代码，可以将其分为以下过程或步骤:
    1)将一个值初始化为一个变量
    2)打印该值
    3)更改该值
    4)打印该值

    这些过程反复进行。这可以用如下循环来代替:

    *   在上面显示的代码中，初始化是 a=1，同样的事情可以在 for 循环中进行。
    *   第二个表达式是条件。条件应该指定循环应该执行多少次。这取决于该过程应该重复的次数。在这种情况下，它应该运行 5 次。**“a”**的值从 1 开始，应打印至其值为 5。所以需要补充的条件是 **a < =5** 。
    *   第三种表达是上升。每次循环变量，这里是“a”，都需要根据预期的代码进行更新。在这里，“a”的值在每次打印操作时递增 1。因此 **a++** 在这种情况下是合适的。
    *   最后一个表达式是 body，它是需要重复执行的操作。这里“a”的值打印在每次执行中。

    下面是在循环的帮助下所需代码的执行:

    ```
    class GFG {
        public static void main(String args[])
        {
            int a;
            for (a = 1; a <= 5; a++) {
                System.out.println(a);
            }
        }
    }
    ```
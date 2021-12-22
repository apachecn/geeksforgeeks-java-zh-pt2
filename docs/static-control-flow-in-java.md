# Java 中的静态控制流

> 原文:[https://www.geeksforgeeks.org/static-control-flow-in-java/](https://www.geeksforgeeks.org/static-control-flow-in-java/)

静态控制流决定了当我们运行包含静态变量、方法和块的 java 类时，将按顺序执行的活动/步骤的顺序。本文将解释静态控制流是如何在 Java 程序执行时发生的。

**先决条件:** [静态区块](https://www.geeksforgeeks.org/g-fact-79/)

静态控制流机制按照确切的时间顺序执行以下 3 个步骤:

1.  从上到下识别静态成员。所有静态变量、方法和块都在这个步骤中被识别。
2.  从上到下执行静态变量赋值和静态块。
3.  最后，在静态控制流程的最后一步执行静态主方法。

**例**:

```
// StaticControlFlow class (Main class)
class StaticControlFlow {
    // initializing static integer a=100
    static int a = 100;

    // static main method
    public static void main(String[] args)
    {
        // calling static method print()
        print();
        System.out.println("Main method has finished its execution");
    }

    // first static block
    static
    {
        // displaying value of a
        System.out.println(a);

        // calling static method print()
        print();
        System.out.println("Inside First Static Block");
    }

    // static method print()
    public static void print()
    {
        // displaying value of b
        System.out.println(b);
    }

    // second static block
    static
    {
        System.out.println("Inside Second Static Block");
    }

    // initializing static integer b=200
    static int b = 200;
}
```

**Output:**

```
100
0
Inside First Static Block
Inside Second Static Block
200
Main method has finished its execution

```

**说明:**
执行上述程序时，静态控制流机制将依次执行 3 个步骤。在第一步中识别静态成员后，两个静态块都从上到下执行。在*第一个静态块*中，变量**‘a’**的值为 100，因为它在执行第一个静态块之前已经被初始化。

但是，在*第二静态块*内，变量**【b】**的值尚未按照静态控制流程初始化。因此，JVM 将打印 0 作为未初始化静态变量的默认值。

然后，在第三步也是最后一步，执行静态主方法。在主方法内部，再次调用静态方法 print()，这一次它打印 b = 200，因为变量“b”在第二步初始化。

**直接和间接引用**

如果我们试图读取并显示静态块中的变量值，则该读取操作称为直接读取。如果我们从静态块中调用一个方法，并且在该方法中，如果我们试图读取一个变量，则该读取操作称为间接读取。

在上面的例子中，当在第一个静态块中打印变量“a”的值时，它被认为是直接读取操作。但是，在同一个静态块中，调用了一个静态方法 print()，并打印了变量“b”的值。这被认为是间接读取操作。

如果一个变量刚刚被 JVM 识别，还没有被它的原始值初始化，那么这个变量就被认为是处于只读间接写状态。在静态控制流程的第一步之后，变量‘a’和‘b’都处于 RIWO 状态。
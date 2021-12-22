# Java 中不可达代码错误

> 原文:[https://www . geesforgeks . org/不可达-java 中的代码错误/](https://www.geeksforgeeks.org/unreachable-code-error-in-java/)

**不可达语句**是指在程序执行过程中不会被执行的语句，称为不可达语句。由于以下原因，这些语句可能无法访问:

*   他们面前有一份申报表
*   在他们面前有一个无限循环
*   在 try 块中引发异常后的任何语句

**可能出现此错误的场景:**

*   **在它们之前有一个返回语句**:当一个返回语句被执行时，那个函数的执行就在那里被停止。因此，此后的任何语句都不会被执行。这将导致无法访问的代码错误。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class GFG {
    public static void main(String args[])
    {

        System.out.println("I will get printed");

        return;

        // it will never run and gives error
        // as unreachable code.
        System.out.println("I want to get printed");
    }
}
```

*   **编译错误:**

> prog.java:11:错误:不可达语句
> System.out.println(“我想打印”)；
> ^
> 1 错误

*   **前面有一个无限循环**:假设在“if”语句里面，如果在 break 语句之后写语句，那么写在“break”关键字下面的语句永远不会执行，因为如果条件为 false，那么循环永远不会执行。如果条件为真，那么由于“break”，它将永远不会执行，因为“break”接受“if”语句之外的执行流。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class GFG {
    public static void main(String args[])
    {
        int a = 2;
        for (;;) {

            if (a == 2)
            {
                break;
                // it will never execute, so
                // same error will be there.
                System.out.println("I want to get printed");
            }
        }
    }
}
```

1.  **编译错误:**

> prog.java:13:错误:不可达语句
> System.out.println(“我想打印”)；
> ^
> 1 错误

*   **抛出异常后的任何语句**:如果我们抛出异常后在 try-catch 块中添加了任何语句，那么这些语句是不可达的，因为出现了异常事件，执行跳转到 catch 块或者 finally 块。抛出后的行不会立即执行。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class GFG {
    public static void main(String args[])
    {

        try {
            throw new Exception("Custom Exception");
            // Unreachable code
            System.out.println("Hello");
        }
        catch (Exception exception) {
            exception.printStackTrace();
        }
    }
}
```

*   **编译错误:**

> prog.java:7:错误:不可达语句
> system . out . println(“Hello”)；
> ^
> 1 错误

*   **写入 continue 后的任意语句**:如果我们在写入 continue 关键字后在循环中添加了任意语句，那么这些语句是不可到达的，因为执行会跳到 for 循环的顶部。continue 之后的行不会立即执行。
    **例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class GFG {
    public static void main(String args[])
    {
        for (int i = 0; i < 5; i++)
        {
            continue;
            System.out.println("Hello");
        }
    }
}
```

*   **编译错误:**

> prog.java:6:错误:不可达语句
> system . out . println(“Hello”)；
> ^
> 1 错误
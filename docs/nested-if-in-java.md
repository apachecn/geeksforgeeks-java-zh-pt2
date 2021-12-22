# 嵌套 if 在 Java 中

> 原文:[https://www.geeksforgeeks.org/nested-if-in-java/](https://www.geeksforgeeks.org/nested-if-in-java/)

一般来说，如果条件像是或否类型一样工作。如果条件满足，它将执行某个代码块。否则，它不会执行代码。让我们看看简单 if 条件的语法。

**语法:**

```
if( condition ){

       statements ;

}
```

### **嵌套 if 条件**

嵌套意味着在。嵌套的 if 条件意味着 if-in-if。嵌套的 if 条件出现在 Java 中的 [**决策语句下**](https://www.geeksforgeeks.org/decision-making-javaif-else-switch-break-continue-jump/) 。if 条件中可能有无限个 if 条件。以下语法表示嵌套 if 条件。

**语法:**

```
if( condition ){

      if( condition ){

                if( condition ){

                         ......
                }
       }
}
```

> **注意–**如果内部条件满足，则只执行外部 If。除了 if 条件，我们还可以写其他条件。

**例 1**

## Java

```
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG
{  
    public static void main(String args[])
    {
        int a=10;
          int b=20;

        if(a==10){
            if(b==20){
                System.out.println("GeeksforGeeks");
            }
        }
    }
}
```

**输出**

```
GeeksforGeeks
```

**代码说明:**

*   In the first step, we have imported the required packages.
*   Next, we created a class name GFG.
*   Next, we wrote the main method.
*   In the main method, we assign values to variables.
*   Using nested if conditions, we have printed a statement.
*   There are two statements that are correct here. Therefore, the statement executes successfully.

**例 2:**

## Java

```
import java.util.*;
import java.lang.*;

class GFG
{  
    public static void main(String args[])
    {
        int a=10;
          int b=20;

        if(a==10){

            if(b!=20){
                System.out.println("GeeksforGeeks");
            }

            else{
                System.out.println("GFG");
            }
        }
    }
}
```

**输出**

```
GFG
```

**代码说明:**

*   In the first step, we have imported the required packages.
*   Next, we created a class name GFG.
*   Next, we wrote the main method.
*   In the main method, we assign values to variables.
*   Using nested if conditions, we have printed a statement.
*   Here, if the inherent conditions are not true. Therefore, other parts are executed.

嵌套 if 条件出现在 Java 的决策语句下。它包含几个分支，其中一个 if 条件在另一个 if 条件内。上面的文章详细介绍了嵌套 if 语句的语法、代码示例和解释。
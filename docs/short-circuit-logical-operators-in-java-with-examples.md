# Java 中的短路逻辑运算符示例

> 原文:[https://www . geesforgeks . org/短路-逻辑-运算符-Java-带示例/](https://www.geeksforgeeks.org/short-circuit-logical-operators-in-java-with-examples/)

在 [Java 逻辑运算符](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)中，如果在完成求值之前，一个逻辑表达式的求值存在于两者之间，则称之为**短路**。短路的发生是因为结果甚至在表达式的完整计算之前就已经清楚了，并且结果被返回。短路评估避免了不必要的工作，并导致高效的处理。

以下是 Java 中出现的各种类型的短路:

#### 1.[和(& & )](https://www.geeksforgeeks.org/operator-in-java-with-examples/) 短路:

在 AND 的情况下，表达式被求值，直到我们得到一个错误的结果，因为结果总是错误的，与进一步的条件无关。如果有一个带有&&(逻辑与)的表达式，并且第一个操作数本身为假，则发生短路，不计算进一步的表达式，并返回假。

**示例:**使用 AND( & &)运算符短路。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate the
// short circuiting using &&

import java.io.*;

class ShortCirAND {
    public static void main(String arg[])
    {

        // Since first operand is false
        // and operator is &&,
        // Evaluation stops and
        // false is returned.
        if (false && true && true) {
            System.out.println("This output "
                               + "will not "
                               + "be printed");
        }
        else {

            System.out.println("This output "
                               + "got printed actually, "
                               + " due to short circuit");
        }

        // Whole expression will be evaluated,
        // as no false is encountered
        // before last condition
        // Therefore no Short circuit
        if (true && true && true) {
            System.out.println("This output "
                               + "gets print"
                               + " as there will be"
                               + " no Short circuit");
        }
        else {

            System.out.println("This output "
                               + "will not "
                               + "be printed");
        }
    }
}
```

**Output**

```
This output got printed actually,  due to short circuit
This output gets print as there will be no Short circuit
```

#### 2. [OR(||)](https://www.geeksforgeeks.org/operator-in-java/) 短路:

在“或”的情况下，表达式被求值，直到我们得到一个真实的结果，因为结果总是真实的，与进一步的条件无关。如果有一个表达式带有||(逻辑或)，并且第一个操作数本身为真，则发生短路，计算停止，并返回真。

**示例:**使用 OR( ||)短路。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// short circuiting using OR

class ShortCirOR {
    public static void main(String arg[])
    {

        // Since first operand is true
        // and operator is ||,
        // Evaluation stops and
        // true is returned.
        if (true || false || false) {
            System.out.println("This output "
                               + "got printed actually, "
                               + " due to short circuit");
        }
        else {
            System.out.println("This output "
                               + "will not "
                               + "be printed");
        }

        // Whole expression will be evaluated,
        // as no true is encountered
        // before last condition
        // Therefore no Short circuit
        if (false || false || true) {
            System.out.println("This output "
                               + "gets print"
                               + " as there will be"
                               + " no Short circuit");
        }
        else {

            System.out.println("This output "
                               + "will not "
                               + "be printed");
        }
    }
}
```

**Output**

```
This output got printed actually,  due to short circuit
This output gets print as there will be no Short circuit
```
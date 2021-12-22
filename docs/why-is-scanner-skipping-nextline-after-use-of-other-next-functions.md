# 为什么扫描仪在使用其他 next 功能后会跳过 nextLine()？

> 原文:[https://www . geesforgeks . org/why-is-scanner-skilling-next line-在使用其他下一个函数之后/](https://www.geeksforgeeks.org/why-is-scanner-skipping-nextline-after-use-of-other-next-functions/)

[java.util.Scanner 类](https://www.geeksforgeeks.org/scanner-class-in-java/)的 [nextLine()](https://www.geeksforgeeks.org/scanner-nextline-method-in-java-with-examples/) 方法使该扫描仪前进通过当前行，并返回跳过的输入。该函数打印当前行的剩余部分，在末尾省略行分隔符。下一个设置为行分隔符之后。由于此方法继续在输入中搜索行分隔符，因此如果不存在行分隔符，它可能会搜索所有输入以寻找要跳过的行。

**语法:**

```
public String nextLine()
```

**<u>next line()方法有什么问题？</u>T3】**

考虑下面的代码示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show the issue with
// nextLine() method of Scanner Class

import java.util.Scanner;

public class ScannerDemo1 {
    public static void main(String[] args)
    {
        // Declare the object and initialize with
        // predefined standard input object
        Scanner sc = new Scanner(System.in);

        // Taking input
        String name = sc.nextLine();
        char gender = sc.next().charAt(0);
        int age = sc.nextInt();
        String fatherName = sc.nextLine();
        String motherName = sc.nextLine();

        // Print the values to check
        // if the input was correctly obtained.
        System.out.println("Name: " + name);
        System.out.println("Gender: " + gender);
        System.out.println("Age: " + age);
        System.out.println("Father's Name: "
                           + fatherName);
        System.out.println("Mother's Name: "
                           + motherName);
    }
}
```

*   当该代码在**输入**下运行时:

```
abc
m
1
xyz
pqr
```

*   **预期输出:**

```
Name: abc
Gender: m
Age: 1
Father's Name: xyz
Mother's Name: pqr
```

*   **实际输出:**

```
Name: abc
Gender: m
Age: 1
Father's Name: 
Mother's Name: xyz
```

如您所见，nextLine()方法跳过要读取的输入，用母亲的名字代替父亲。因此，预期输出与实际输出不匹配。这个错误很常见，会导致很多问题。

**<u>为什么会出现这个问题？</u>**
出现此问题是因为，当[扫描仪类](https://www.geeksforgeeks.org/scanner-class-in-java/)的 [nextInt()](https://www.geeksforgeeks.org/scanner-nextint-method-in-java-with-examples/) 方法用于读取人的年龄时，如预期的那样，它会将值 1 返回给可变年龄。但是光标在读完 1 之后，仍然停留在它的后面。

```
abc
m
1_ // Cursor is here
xyz
pqr
```

所以当使用[扫描仪类](https://www.geeksforgeeks.org/scanner-class-in-java/)的 [nextLine()](https://www.geeksforgeeks.org/scanner-nextline-method-in-java-with-examples/) 方法读取父亲的名字时，该方法从光标的当前位置开始读取。在这种情况下，它将在 1 之后开始读取。所以 1 之后的下一行只是一个新行，用' \n '字符表示。因此，父亲的名字只是' \n '。

**<u>如何解决这个问题？</u>**
这个问题可以通过以下两种方式解决:

1.读取整数的完整行并将其转换为整数，或者

**语法:**

```
// Read the complete line as String
// and convert it to integer
int var = Integer.parseInt(sc.nextLine());
```

虽然此方法不适用于字节字符后的输入字符串(Byte.parseByte(sc.nextLine())。第二种方法适用于这种情况。

2.通过使用 nextLine()方法消耗剩余的新行。

**语法:**

```
// Read the integer
int var = sc.nextInt();

// Read the leftover new line
sc.nextLine();
```

下面的例子展示了如何用 nextLine()方法解决这个问题:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to solve the issue with
// nextLine() method of Scanner Class

import java.util.Scanner;
import java.io.*;
import java.lang.*;

class ScannerDemo1 {
    public static void main(String[] args)
    {
        // Declare the object and initialize with
        // predefined standard input object
        Scanner sc = new Scanner(System.in);

        // Taking input
        String name = sc.nextLine();
        char gender = sc.next().charAt(0);

        // Consuming the leftover new line
        // using the nextLine() method
        sc.nextLine();

        // reading the complete line for the integer
        // and converting it to an integer
        int age = Integer.parseInt(sc.nextLine());

        String fatherName = sc.nextLine();
        String motherName = sc.nextLine();

        // Print the values to check
        // if the input was correctly obtained.
        System.out.println("Name: " + name);
        System.out.println("Gender: " + gender);
        System.out.println("Age: " + age);
        System.out.println("Father's Name: "
                           + fatherName);
        System.out.println("Mother's Name: "
                           + motherName);
    }
}
```

*   当该代码在**输入**下运行时:

```
abc
m
1
xyz
pqr
```

*   **预期输出:**

```
Name: abc
Gender: m
Age: 1
Father's Name: xyz
Mother's Name: pqr
```

*   **实际输出:**

```
Name: abc
Gender: m
Age: 1
Father's Name: xyz
Mother's Name: pqr
```
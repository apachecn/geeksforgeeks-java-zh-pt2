# Java 中的类型擦除

> 原文:[https://www.geeksforgeeks.org/type-erasure-java/](https://www.geeksforgeeks.org/type-erasure-java/)

**先决条件:** [泛型](https://www.geeksforgeeks.org/generics-in-java/)
泛型概念是在 Java 语言中引入的，以在编译时提供更严格的类型检查，并支持泛型编程。实现泛型的方法，Java 编译器将**类型擦除**应用于:

*   如果类型参数是无界的，则将泛型类型中的所有类型参数替换为它们的边界或对象。因此，生成的字节码只包含普通的类、接口和方法。
*   如有必要，插入类型转换以保护类型安全。
*   生成桥接方法以在扩展泛型类型中保留[多态性](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/)。

一般来说，编译后的泛型代码实际上只使用 java.lang.Object，无论您在哪里谈论 T(或其他类型参数)——并且有一些元数据告诉编译器它确实是泛型类型。当您针对泛型类型或方法编译一些代码时，编译器会计算出您真正的意思(即 T 的类型参数是什么)，并在编译时验证您正在做正确的事情，但是发出的代码仍然只是用 java.lang.Object 的术语说话——编译器会在必要时生成额外的强制转换。在执行时，列表和列表完全相同；额外的类型信息已被编译器删除。

**根据计划，类型擦除是如何工作的？**

```
// Here, T is bounded by Object i.e. java.lang.Object
class GFG<T> {
// Here, T will be replaced by default i.e. Object
    T obj; 

    GFG(T o)
    {
        obj = o;
    }
    T getob()
    {
        return obj;
    }
}
```

**编译后，代码被默认对象替换，如下所示:**

```
class GFG
{
// Here, T will be replaced by default i.e. Object
    Object obj;
    GFG(Object o)
    {
        obj=o;
    }
    Object getob()
    {
        return obj;
    }
}

```

```
// Here, T is bounded by Object i.e. java.lang.Object
class Geeks<T extends String> {

 // Here, T will be replaced by String i.e. java.lang.String
    T str;
    Geeks(T o)
    {
        str = o;
    }
    T getob()
    {
        return str;
    }
}
```

**编译后，代码替换为如下字符串:**

```
class Geeks
{

//Here, T will be replaced by String i.e. java.lang.String
    String str;

    Geeks(String o)
    {
        str=o;
    }
    String getob()
    {
        return str;
    }
}

```

**注:**以上两个类编译完成后，我们可以同时查看两个类的内容。编译后，在 GFG，类 T 将被对象替换，在极客类 T 将被字符串替换。我们可以通过运行 **javap className** 命令编译的代码来检查内容。

**类型擦除实施**

```
// Java program to illustrate
// concept of TypeErasure

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;
public class GenericsErasure {
    public static void main(String args[])
    {
        List<String> list = new ArrayList<String>();
        list.add("Hello");
        Iterator<String> iter = list.iterator();
        while (iter.hasNext()) {
            String s = iter.next();
            System.out.println(s);
        }
    }
}
```

**解释:**这里我们在编译代码的时候，它不会向控制台屏幕抛出任何警告消息，因为这里我们使用的是 Type Erasure。

```
// Java program to illustrate
// concept of TypeErasure
import java.io.PrintStream;
import java.util.*;

public class GenericsErasure {

    public GenericsErasure()
    {
    }

    public static void main(String args[])
    {
        List list = new ArrayList();
        list.add("Hello");
        String s;
        for (Iterator iter = list.iterator(); iter.hasNext();
             System.out.println(s))
            s = (String)iter.next();
    }
}
```

**解释:**在这里，当我们编译代码时，我们会从编译器那里得到一些提示，即 GenericsErasure.java 使用了未经检查或不安全的操作。

**参考:**
[类型擦除](https://docs.oracle.com/javase/tutorial/java/generics/erasure.html)
[堆栈溢出](https://stackoverflow.com/questions/313584/what-is-the-concept-of-erasure-in-generics-in-java)
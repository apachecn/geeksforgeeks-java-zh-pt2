# Java 中保护敏感数据的标准实践

> 原文:[https://www . geeksforgeeks . org/Java 中保护敏感数据的标准做法/](https://www.geeksforgeeks.org/standard-practices-for-protecting-sensitive-data-in-java/)

Java 平台通过内存安全等特性，为执行不同权限级别的代码提供了环境，为安全系统提供了强大的基础。Java 语言和虚拟机使应用程序开发高度抵抗常见的编程错误、堆栈粉碎和缓冲区溢出攻击，这些攻击在 C 和 C++编程语言中是可能的。然而，通过易受攻击的编程实践产生的错误可能会产生严重的安全后果，并且可能出现在堆栈的任何一层。在本文中，我们将列出 Java 中保护敏感数据的一些标准编程实践。

安全编码准则包含如下参数:

1.  Release resources
2.  Destroy sensitive information from anomalies
3.  Avoid dynamic SQL
4.  Restrict accessibility
5.  Limit scalability

让我们分别讨论这些实践如何在 java 中帮助保护我们的敏感数据，并将在需要更好理解的地方借助示例代码进行讨论。

### 1.释放资源

执行期间使用的应用程序资源，如打开的文件、内存、对象和锁，如果在使用后没有释放，可能会导致处理过程中的错误、重复和死锁。因此，资源应该总是在使用之后通过结合像执行方法(使用 lambda)和资源尝试语法这样的技术来释放。

**例 1:** 举例说明执行绕过方法

```java
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Inserting code here

        // Execute Around pattern using Lambda
        // Clean-up is taken care of by lambda

        // Out lambda expression
        long sum = readFileBuffered(InputStream in -> {
            long current = 0;
            for (;;) {
                int b = in.read();
                if (b == -1) {
                    return current;
                }

                current += b;
            }
        });
    }
}
```

**示例 2:** 演示资源试用语法

```java
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Inserting code here

        // Try-with-resource syntax
        public R readFileBuffered(
            InputStreamHandler handler) throws IOException
        {

            // Rry statement with one or more resources
            try (final InputStream in
                 = Files.newInputStream(path)) {
                handler.handle(new BufferedInputStream(in));
            }

            // By now the resource is closed
            // at the end of the statement execution
        }
    }
}
```

### 2.从异常中销毁敏感信息

许多形式的攻击涉及猜测或知道文件的位置，异常可能包括关于系统配置和内部的敏感信息。抛出异常(如 Java . io . FileNoFoundException)的堆栈跟踪可以包括系统的文件路径，攻击者可以使用这些路径回溯到系统文件并锁定敏感数据。因此，在将内部异常传播给上游调用方之前，应该捕获并清理它们。

### **3。**避免动态 SQL

来自不可信来源的动态创建的 SQL 语句可能包含受命令注入影响的输入，这意味着通过 SQL 语句注入恶意代码以直接影响数据。相反，应该使用参数化的 SQL 语句，如[Java . SQL . preparedstatement](https://www.geeksforgeeks.org/how-to-use-preparedstatement-in-java/#:~:text=A%20PreparedStatement%20is%20a%20pre,to%20execute%20a%20parameterized%20query.)或[Java . SQL . callablestatement](https://www.geeksforgeeks.org/how-to-use-callable-statement-in-java-to-call-stored-procedure/)，以便语句被预编译，并且只需要插入参数就可以执行。

**样品**T0】

### **4。**限制可达性

如果类成员、方法、构造函数和接口不是 API 的一部分，则应该声明为私有的或受保护的，以避免暴露它们的实现。如果实现被封装，并且不向外部实体公开，那么安全性将得到维护，因为外部人员将无法更改内部结构。

### **5。**限制延展性

如果类或方法没有被声明为最终的，那么攻击者可以恶意地重写它们。不允许继承的类更容易实现并验证其安全性。比起传承，更喜欢[构图](https://www.geeksforgeeks.org/composition-in-java/#:~:text=Composition%20offers%20better%20test%2Dability,the%20behavior%20of%20your%20program.)。

**示例**通过合成和最终类

```java
// Class 1
// Helper class- Book class
class Book {

    // Member variables of Book class
    public String title;
    public String author;

    // Parameterized constructor of Book class
    Book(String title, String author)
    {
        // This refers to current object itself
        this.title = title;
        this.author = author;
    }
}

// Class 2
// Helper class
// Unsubclassable class Library with composed behavior.
public final class Library {

    // Composition
    private final List<Book> books;

    // Hiding the constructor of this class
    // by declaring it private
    private Library(Book book)
    {
        books = new ArrayList<Book>();
    }

    // Method of this class
    // Guarded Construction of class methods
    private void createLibrary(Book book)
    {
        // ...validate any arguments...

        // ...perform security checks...

        // adding elements to the book
        books.add(book);
    }
} 
```

限制延展性

在本文中，我们讨论了一些常见的陷阱和相关的解决方案。因此，最小化漏洞的最有效方法是明显没有缺陷，而不是没有明显的缺陷。为了生产安全的 Java 应用程序，Java 程序员可以遵循这些实践。
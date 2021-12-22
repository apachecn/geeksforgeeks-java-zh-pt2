# 在 Java 中使用静态变量

> 原文:[https://www . geesforgeks . org/using-static-variables-in-Java/](https://www.geeksforgeeks.org/using-static-variables-in-java/)

这里我们将讨论 java 中的静态变量。Java 实际上没有全局变量的概念。要在 java 中定义一个全局变量，需要使用关键字 static。下面讨论静态变量的优点。现在极客们你们一定想知道静态变量有什么优点，为什么要并入我们的程序。现在我们用一个实时的例子来说明我们为什么要使用它。

**图解:**员工目录

假设 NIT Agartala 的生产工程系有 25 名学生。所有学生都有其唯一的注册号、注册号和姓名。所以在这种情况下，实例数据成员是好的。现在，每次创建对象时，所有实例数据成员都将获得内存。这里的“部门”是指所有对象的共同财产。如果我们将它设为静态，这个字段将只获得一次内存。

因此，静态变量可以用来指所有对象的公共属性(对于每个对象来说不是唯一的)，例如，学生的大学名称、员工的公司名称、公司的首席执行官等。它使程序内存高效(即节省内存)。

**示例**

## Java

```
//  Java Program to show the Advantages of Static Variable

// Class 1
class emp {

    // Attributes of employees
    int id;
    String name;
    int salary;
    // Here we are declaring CEO as a static variable
    static String ceo;

    // Constructors of this class
    emp(int id, String name, int salary, String ceo)
    {
        // This keyword refers to current instance itself
        this.id = id;
        this.name = name;
        this.salary = salary;
        this.ceo = ceo;
    }

    // Method of this class
    void display()
    {
        // Print all associated attributes
        System.out.println("ID: " + id + ", "
                           + "Name:: " + name + ", "
                           + "Salary: {content}quot; + salary + " & "
                           + "CEO:: " + ceo);
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of class 1
        // Object 1
        emp Monodwip
            = new emp(1, "Monodwip", 30000, "Rinkel");

        // Object 2
        emp Mukta = new emp(2, "Mukta", 50000, "Rinkel");

        // We have changed the CEO for Subham, As CEO is
        // declared static, sowill change for all the
        // objects

        // Object 3
        emp Subham = new emp(3, "Subham", 40000, "Arnab");

        // Calling display() method over all objects
        Monodwip.display();
        Mukta.display();
        Subham.display();
    }
}
```

**输出**

```
ID: 1, Name:: Monodwip, Salary: $30000 & CEO:: Arnab
ID: 2, Name:: Mukta, Salary: $50000 & CEO:: Arnab
ID: 3, Name:: Subham, Salary: $40000 & CEO:: Arnab

```

输出解释:

从上面的输出中，我们可以看到所有对象的 Rinkel 都被 Arnab 替换了，因此证明了静态变量的使用是正确的。
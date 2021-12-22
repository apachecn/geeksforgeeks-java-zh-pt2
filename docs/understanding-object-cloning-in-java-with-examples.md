# 用示例理解 Java 中的对象克隆

> 原文:[https://www . geesforgeks . org/understanding-object-cloning-in-Java-with-examples/](https://www.geeksforgeeks.org/understanding-object-cloning-in-java-with-examples/)

在本文中我们讨论了**可克隆接口**表示某个类已经提供了安全的 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 。为了理解克隆意味着什么，回想一下当您复制一个保存对象引用的变量时会发生什么。原件和副本是对同一对象的引用。这意味着原件和副本是相互依赖的，也就是说，一个副本的改变也会导致另一个副本的改变。

如果我们想让一个复制品成为一个新的物体，它的生命开始时与原来的一模一样，但是它的状态会随着时间而改变，我们必须使用 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 。

**[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 是在 **[对象类](https://www.geeksforgeeks.org/object-class-in-java/)** 中声明 **[受保护的](https://www.geeksforgeeks.org/access-modifiers-java/)** ，所以我们的代码不能简单地调用 **[obj.clone()](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 。现在我们可能会问，受保护的方法不是可以从任何子类访问的吗？不是每个类都是**对象**的子类吗？幸运的是，受保护访问的规则要微妙得多。子类可以调用受保护的 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 来克隆自己的对象。我们必须将克隆重新定义为 **[公共的](https://www.geeksforgeeks.org/access-modifiers-java/)** 可以被任何方法访问。

即使**克隆**的默认实现已经足够了，你还是需要实现**可克隆**接口，重新定义 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 为**公共**，调用 **[公共](https://www.geeksforgeeks.org/access-modifiers-java/)** 。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Student implements Cloneable {

    // raise visibility level to public
    // and change the return type
    public Student clone()
        throws CloneNotSupportedException
    {
        return (Student)super.clone();
    }
    .
        .
        .
}
```

您刚才看到的 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 对 **Object.clone** 提供的副本没有任何功能。它只是将方法 **[公开](https://www.geeksforgeeks.org/access-modifiers-java/)** 并改变其[返回类型](https://www.geeksforgeeks.org/return-keyword-java/)。为了进行更深入的复制，我们必须克隆可变实例字段。

这是**修改版**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Student implements Cloneable {

    // other components

    public Student clone()
        throws CloneNotSupportedException
    {

        // call Object.clone()
        Student obj = (Student)super.clone();

        // clone mutable fields
        obj.birthDay = (Date)birthDay.clone();
    }
}
```

每当在不实现**可克隆**接口的类上调用**克隆**时，**对象**的 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 将尝试抛出**类不支持的异常**。

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.Date;
import java.util.GregorianCalendar;

public class Employee implements Cloneable {

    private String name;
    private double salary;
    private Date hireDay;

    public Employee(String name, double salary)
    {
        this.name = name;
        this.salary = salary;
        hireDay = new Date();
    }

    public Employee clone()
        throws CloneNotSupportedException
    {

        // call Object.clone()
        Employee obj = (Employee)super.clone();

        // clone mutable fields
        obj.hireDay = (Date)hireDay.clone();

        return obj;
    }

    // Set the hireDay to a given date
    public void setHireDay(int year, int month, int day)
    {

        Date newHireDay
            = new GregorianCalendar(year,
                                    month - 1,
                                    day)
                  .getTime();

        // instance field mutation
        hireDay.setTime(newHireDay.getTime());
    }

    public void raiseSalary(double byPercent)
    {

        double raise = salary * byPercent / 100;
        salary += raise;
    }

    public String toString()
    {
        return ("Employee[name=" + name
                + ", salary=" + salary
                + ", hireDay=" + hireDay
                + "]");
    }

    // main
    public static void main(String[] args)
    {

        try {

            Employee original
                = new Employee("ABC X. YZ", 50000);

            original.setHireDay(2000, 1, 1);
            Employee copy = original.clone();

            copy.raiseSalary(10);
            copy.setHireDay(2002, 12, 31);

            System.out.println("original= " + original);
            System.out.println("copy= " + copy);
        }

        catch (CloneNotSupportedException e) {
            e.printStackTrace();
        }
    }
}
```

**Output:**

> 原件=员工[姓名=ABC X. YZ，工资=50000.0，hireDay = 2000 年 1 月 1 日星期六 00:00:00:00 UTC]
> 复印件=员工[姓名=ABC X. YZ，工资=55000.0，hireDay = 2002 年 12 月 31 日星期二 00:00:00 UTC]

**克隆的优势:**

*   在 Java 中， ['= '(赋值)运算符](https://www.geeksforgeeks.org/operators-in-java/)不能用于克隆，因为它只是创建了引用变量的副本。为了克服这种差异， **[对象类](https://www.geeksforgeeks.org/object-class-in-java/)** 的 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 可以用于赋值运算符。
*   **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 是类**对象**的[受保护的](https://www.geeksforgeeks.org/access-modifiers-java/)方法，也就是说只有 Employee 类可以克隆 Employee 对象。这意味着除了 Employee 之外，没有其他类可以克隆 Employee 对象，因为它不知道 Employee 类的属性。

**克隆在 Java 中的应用**:

*   它允许对对象进行逐字段复制，这在处理具有相似特征的对象时非常方便。
*   默认的 **[克隆()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)** 可以通过在可变子对象上调用**克隆**来修补。
# Java 中继承的需求是什么？

> 原文:[https://www . geesforgeks . org/什么是 java 中需要的继承/](https://www.geeksforgeeks.org/what-is-the-need-of-inheritance-in-java/)

众所周知，继承是面向对象编程语言最重要的特性之一，无论是 Java、C++还是任何其他面向对象编程语言。但是继承的必要性是什么呢？为什么它是一个如此重要的概念

[**继承**](https://www.geeksforgeeks.org/inheritance-in-java/) 可以定义为一个对象获取父对象所有属性(即数据成员)和行为(即成员函数或方法)的机制。

继承的基本思想是从现有类(称为父类或基类或超类)创建新类(称为子类或派生类或子类)。也就是说，子类继承父类的属性(方法和字段)。

认为没有继承就能完成某件事是对时间和资源的滥用，因为我们不得不一次又一次地编写相同的代码。

让我们举个例子，三个班级人，员工和学生有一些属性，一些共同的和一些不同的。请参见下面的代码。

## 爪哇

```java
// Java program without inheritance
import java.io.*;
import java.math.BigDecimal;

// class person
class Person {

    private String name;
    private int age;

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }

    public void setAge(int age) { this.age = age; }

    public String toString()
    {
        return String.format(
            "Person :- name : %s , age : %d", name, age);
    }
}

//class student
class Student {

    private String name;
    private int age;
    private int rollno;
    private String school;

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }

    public void setAge(int age) { this.age = age; }

    public int getRollno() { return rollno; }

    public void setRollno(int rollno)
    {
        this.rollno = rollno;
    }

    public String getSchool() { return school; }

    public void setSchool(String school)
    {
        this.school = school;
    }

    public String toString()
    {
        return String.format(
            "Student :- name : %s , age : %d , roll : %d , school : %s",
            name, age, rollno, school);
    }
}

//class Employee
class Employee {

    private String name;
    private int age;
    private double salary;
    private String organisation;

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }

    public void setAge(int age) { this.age = age; }

    public double getSalary() { return salary; }

    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    public String getOrganisation() { return organisation; }

    public void setOrganisation(String organisation)
    {
        this.organisation = organisation;
    }

    public String toString()
    {
        return String.format(
            "Employee :- name : %s , age : %d , organisation : %s , salary : %f",
            name, age, organisation, salary);
    }
}

// class PersonRunner
public class PersonRunner {

    public static void main(String[] args)
    {
        Person person = new Person();
        Student student = new Student();
        Employee employee = new Employee();

        person.setName("Saurabh");
        person.setAge(20);

        student.setName("Prateek");
        student.setAge(21);
        student.setRollno(101);
        student.setSchool("New Era HS");

        employee.setName("Sushant");
        employee.setAge(25);
        employee.setOrganisation("GeeksforGeeks");
        employee.setSalary(50000.00);

        System.out.println(person);
        System.out.println(student);
        System.out.println(employee);
    }
}
```

**输出**

```java
Person :- name : Saurabh , age : 20
Student :- name : Prateek , age : 21 , roll : 101 , school : New Era HS
Employee :- name : Sushant , age : 25 , organisation : GeeksforGeeks , salary : 50000.000000
```

请注意，我们必须在学生和员工类中再次编写已经在 Person 类中编写的相同代码。这需要时间和记忆。

现在仔细阅读下面我们使用继承的代码。

## 爪哇

```java
// Java program with inheritance
import java.io.*;

class Person {

    private String name;
    private int age;

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }

    public void setAge(int age) { this.age = age; }

    public String toString()
    {
        return String.format(
            "Person :- name : %s , age : %d", getName(),
            getAge());
    }
}

// Student class is inheriting the properties of Person
// class( through extend keyword) Therefore, we don't need to
// declare name and age (and their related methods which are
// covered in Person) again.
class Student extends Person {

    private int rollno;
    private String school;

    public int getRollno() { return rollno; }

    public void setRollno(int rollno)
    {
        this.rollno = rollno;
    }

    public String getSchool() { return school; }

    public void setSchool(String school)
    {
        this.school = school;
    }

    public String toString()
    {
        return String.format(
            "Student :- name : %s , age : %d , roll : %d , school : %s",
            getName(), getAge(), getRollno(), getSchool());
    }
}

// Employee class is inheriting the properties of Person
// class( through extend keyword) Therefore, we don't need to
// declare name and age (and their related methods which are
// covered in Person) again.
class Employee extends Person {

    private double salary;
    private String organisation;

    public double getSalary() { return salary; }

    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    public String getOrganisation() { return organisation; }

    public void setOrganisation(String organisation)
    {
        this.organisation = organisation;
    }

    public String toString()
    {
        return String.format(
            "Employee :- name : %s , age : %d , organisation : %s , salary : %f",
            getName(), getAge(), getOrganisation(),
            getSalary());
    }
}

public class PersonRunner {

    public static void main(String[] args)
    {
        Person person = new Person();
        Student student = new Student();
        Employee employee = new Employee();

        person.setName("Saurabh");
        person.setAge(20);

        student.setName("Prateek");
        student.setAge(21);
        student.setRollno(101);
        student.setSchool("New Era HS");

        employee.setName("Sushant");
        employee.setAge(25);
        employee.setOrganisation("GeeksforGeeks");
        employee.setSalary(50000.00);

        System.out.println(person);
        System.out.println(student);
        System.out.println(employee);
    }
}
```

**输出**

```java
Person :- name : Saurabh , age : 20
Student :- name : Prateek , age : 21 , roll : 101 , school : New Era HS
Employee :- name : Sushant , age : 25 , organisation : GeeksforGeeks , salary : 50000.000000
```

请注意，与第一个没有使用继承的示例相比，我们在上面的示例中使用继承时编写的代码更少，因此我们不得不一次又一次地定义名称、年龄及其相关方法。

也就是说，我们已经利用了可重用性的概念，因为我们已经一次又一次地重用了 Person 类中编写的代码。

此外，上面的示例显示了方法重写(因为 Person 类的 toString 函数在 Student 和 Employee 类中都被重写，这也是继承的一个主要特性。

因此，它得出结论，继承的主要目的是实现可重用性的概念，节省我们的时间和资源，并在不同的类之间创建更好的连接，并实现方法重写。
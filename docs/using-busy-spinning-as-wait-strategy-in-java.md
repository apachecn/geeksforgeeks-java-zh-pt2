# 在 Java 中使用忙转作为等待策略

> 原文:[https://www . geesforgeks . org/使用-busy-spin-as-wait-in-Java 策略/](https://www.geeksforgeeks.org/using-busy-spinning-as-wait-strategy-in-java/)

繁忙旋转是一种等待策略，在这种策略中，一个线程等待由另一个线程设置的某个条件发生。这里，等待线程连续循环，而不释放 CPU 周期。这导致了糟糕的性能，因为等待线程浪费了 CPU 周期。

非常自然地适合这种策略的一个经典用例是生产者-消费者问题。生产者线程向队列添加项目。消费者线程在消费队列中的项目之前一直等到生产者生产出一个项目。消费者线程在等待时保持 CPU 周期，因此存在 CPU 资源的浪费，这些资源可以被其他线程用于一些其他处理。

另一个更好理解这个策略的例子是到考虑一个顾客从披萨柜台点披萨。下订单后，顾客每 5 秒钟就会问柜台的人他的订单是否准备好了。在这里，等待该订单的顾客可以利用他的时间进行其他活动，例如与他的朋友交谈、浏览最新的新闻等等，而不是忙于检查他的比萨饼订单的状态。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate  Busy Spinning as Wait
// Strategy

// Importing input output classes
import java.io.*;
// Importing List class from java.util package
import java.util.List;

// Class 1
// Helper class
public class Pizza {

    private String base;
    public String getBase() { return base; }

    public void setBase(String base) { this.base = base; }

    public List<String> getToppings() { return toppings; }

    public void setToppings(List<String> toppings)
    {
        this.toppings = toppings;
    }

    private List<String> toppings;

    public Pizza(String base, List<String> toppings)
    {
        super();
        this.base = base;
        this.toppings = toppings;
    }

    public void make()
    {
        System.out.println("Making pizza");
    }
}

// Class 2
// Helper class
public class Customer implements Runnable {

    PizzaMaker pizzaMaker;

    public Customer(PizzaMaker pizzaMaker)
    {
        this.pizzaMaker = pizzaMaker;
    }

    public void run()
    {
        while (this.pizzaMaker.isInProgress) {
            System.out.println(
                Thread.currentThread().getName()
                + ":-Pizza order complete??");
            System.out.println("--Busy Spinning---");
            try {
                Thread.sleep(1000);
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }

        System.out.println(
            "Received the ordered pizza:-"
            + Thread.currentThread().getName());
        System.out.println("Base of the pizza is : "
                           + pizzaMaker.pizza.getBase());
        System.out.println(
            "Topings are : "
            + pizzaMaker.pizza.getToppings());
    }
}

// Class 3
// Helper class
public class PizzaMaker implements Runnable {

    Pizza pizza;
    boolean isInProgress;
    public PizzaMaker(Pizza pizza)
    {
        this.pizza = pizza;
        this.isInProgress = true;
    }

    public void run()
    {
        System.out.println("Pizza order in progress");
        pizza.make();
        try {
            Thread.sleep(3000);
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println(
            " Making of pizza  with base :"
            + this.pizza.getBase() + " and toppings as "
            + this.pizza.getToppings() + " is complete :- "
            + Thread.currentThread().getName());
        this.isInProgress = false;
    }
}

// Class 4
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        //
        String base = "thick crust base";

        // Creating a List of String type
        List<String> toppings = new ArrayList<>();

        // Adding elements to the object
        toppings.add("tomato");
        toppings.add("corn");
        toppings.add("cheese");
        toppings.add("olive");

        Pizza pizza = new Pizza(base, toppings);

        PizzaMaker pizzaMaker = new PizzaMaker(pizza);
        Customer customer = new Customer(pizzaMaker);
        Thread pizzaMakerThread
            = new Thread(pizzaMaker, "pizzaMakerThread");
        Thread customerThread
            = new Thread(customer, "customerThread");

        pizzaMakerThread.start();
        customerThread.start();
    }
}
```

**输出:**

```java
Pizza order in progress
Making pizza
customerThread:-Pizza order complete??
--Busy Spinning---
customerThread:-Pizza order complete??
--Busy Spinning---
customerThread:-Pizza order complete??
--Busy Spinning---
 Making of pizza  with base :thick crust base and toppings as [tomato, corn, cheese, olive] is complete :- pizzaMakerThread
Received the ordered pizza:-customerThread
Base of the pizza is : thick crust base
Topings are : [tomato, corn, cheese, olive]
```

输出解释:

在这个例子中，我们有两个实现 Runnable 接口的类。调用 **PizzaMaker** 构造函数时，它将布尔变量 isInProgress 设置为 true，这意味着它已经收到了 pizza 订单，正在制作 pizza。在 run()中，它调用比萨的 make()。比萨制作完成后，它会将 isInProgress 布尔变量设置为 false。**客户**线程通过在循环内连续循环来执行繁忙的旋转，同时通过布尔变量 isInProgress 检查订单的状态。当 PizzaMaker 类将该变量设置为 false 时，客户线程继续进一步处理。更好的方法是从对象类中实现等待、通知和通知()方法。等待条件得到满足的线程将释放 CPU 资源并执行一些其他任务。当某个其他线程设置了该线程正在等待的条件时，它会通过 notify()方法通知等待的线程。
# Java 中的单一责任原则举例

> 原文:[https://www . geeksforgeeks . org/单一责任-原则-Java-带示例/](https://www.geeksforgeeks.org/single-responsibility-principle-in-java-with-examples/)

[SOLID](https://www.geeksforgeeks.org/solid-principle-in-programming-understand-with-real-life-examples/) 是首字母缩略词，用于指代软件开发中遵循的一组五个重要原则。该原则是以下给出的五个原则的首字母缩略词……

2.  [[On/Off Principle]](https://www.geeksforgeeks.org/open-closed-principle-in-java-with-examples/)
3.  Liskov substitution principle (LSP)
4.  Interface separation principle (ISP)
5.  Dependence inversion principle (DIP)

在这篇文章中，我们将学习更多关于单一责任原则的知识。顾名思义，它规定所有的类和模块应该只有一个明确的职责。按照**罗伯特·C·马丁**、

> T3] There should be one in a class, and there is only one reason to change.

这意味着当我们设计我们的类时，我们需要确保我们的类只负责一个任务或功能，并且当那个任务/功能有变化时，只有那时，那个类才应该变化。

在软件的世界里，变化是唯一不变的因素。当需求改变时，当我们的类不遵守这个原则时，我们会对我们的类做太多的改变，以使我们的类适应新的业务需求。这可能涉及许多副作用、重新测试和引入新的 bug。此外，我们的依赖类需要改变，从而重新编译类和改变测试用例。因此，需要重新测试整个应用程序，以确保新功能不会破坏现有的工作代码。

一般来说，在长时间运行的软件应用程序中，当出现新的需求时，开发人员倾向于向现有代码中添加新的方法和功能，这使得类变得臃肿，难以测试和理解。查看现有的类，看看新的需求是否适合现有的类，或者是否应该为相同的类设计一个新的类，这总是一个很好的做法。

**单一责任原则的好处**

*   When an application has multiple classes, and each class follows this principle, the applicable one becomes easier to maintain and understand.
*   The code quality of the application is better, so there are fewer defects.
*   It's easy to recruit new members, and they can start contributing more quickly.
*   Testing and writing test cases are much simpler.

**示例**

在 java 世界中，我们有很多遵循这个原则的框架。JSR 380 验证 API 就是一个遵循这一原则的好例子。它有像@NotNull、@Max、@MIn、@Size 这样的注释，这些注释应用于 bean 属性，以确保 bean 属性满足特定的标准。因此，验证 API 只负责在 bean 属性上应用验证规则，并在 bean 属性与特定标准不匹配时发出错误消息

另一个例子是负责所有 CRUD 操作的 Spring Data JPA。它的一个职责是定义一种标准化的方式来存储和检索持久存储中的实体数据。它通过消除编写样板 JDBC 代码将实体存储在数据库中的繁琐任务，简化了开发工作。

总的来说，Spring 框架也是单一责任在实践中的一个很好的例子。Spring 框架相当庞大，有许多模块——每个模块都服务于一个特定的职责/功能。我们只根据需要在依赖 pom 中添加相关模块。

让我们再看一个例子来更好地理解这个概念。考虑一个食品配送应用程序，它接受食品订单，计算账单，并将其交付给客户。对于要执行的每个任务，我们可以有一个单独的类，然后主类可以调用这些类来一个接一个地完成这些操作。

## 爪哇

```
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        Customer customer1 = new Customer();
        customer1.setName("John");
        customer1.setAddress("Pune");
        Order order1 = new Order();
        order1.setItemName("Pizza");
        order1.setQuantity(2);
        order1.setCustomer(customer1);

        order1.prepareOrder();

        BillCalculation billCalculation
            = new BillCalculation(order1);
        billCalculation.calculateBill();

        DeliveryApp deliveryApp = new DeliveryApp(order1);
        deliveryApp.delivery();
    }
}

class Customer {
    private String name;
    private String address;
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getAddress() { return address; }
    public void setAddress(String address)
    {
        this.address = address;
    }
}

class Order {

    private Customer customer;
    private String orderId;
    private String itemName;
    private int quantity;
    private int totalBillAmt;

    public Customer getCustomer() { return customer; }
    public void setCustomer(Customer customer)
    {
        this.customer = customer;
    }
    public String getOrderId() { return orderId; }
    public void setOrderId(String orderId)
    {
        Random random = new Random();

        this.orderId = orderId + "-" + random.nextInt(500);
    }
    public String getItemName() { return itemName; }
    public void setItemName(String itemName)
    {
        this.itemName = itemName;
        setOrderId(itemName);
    }
    public int getQuantity() { return quantity; }
    public void setQuantity(int quantity)
    {
        this.quantity = quantity;
    }
    public int getTotalBillAmt() { return totalBillAmt; }
    public void setTotalBillAmt(int totalBillAmt)
    {
        this.totalBillAmt = totalBillAmt;
    }

    public void prepareOrder()
    {
        System.out.println("Preparing order for customer -"
                           + this.getCustomer().getName()
                           + " who has ordered "
                           + this.getItemName());
    }
}

class BillCalculation {

    private Order order;
    public BillCalculation(Order order)
    {
        this.order = order;
    }

    public void calculateBill()
    {
        /* In the real world, we would want a kind of lookup
          functionality implemented here where we look for
          the price of each item included in the order, add
          them up and add taxes, delivery charges, etc on
          top to reach the total price. We will simulate
          this behaviour here, by generating a random number
          for total price.
        */
        Random rand = new Random();
        int totalAmt
            = rand.nextInt(200) * this.order.getQuantity();

        this.order.setTotalBillAmt(totalAmt);
        System.out.println("Order with order id  "
                           + this.order.getOrderId()
                           + " has a total bill amount of "
                           + this.order.getTotalBillAmt());
    }
}

class DeliveryApp {

    private Order order;
    public DeliveryApp(Order order) { this.order = order; }

    public void delivery()
    {
        // Here, we would want to interface with another
        // system which actually assigns the task of
        // delivery to different persons
        // based on location, etc.
        System.out.println("Delivering the order");
        System.out.println(
            "Order with order id as "
            + this.order.getOrderId()
            + " being delivered to "
            + this.order.getCustomer().getName());
        System.out.println(
            "Order is to be delivered to: "
            + this.order.getCustomer().getAddress());
    }
}
```

**输出**

```
Preparing order for customer -John who has ordered Pizza
Order with order id  Pizza-57 has a total bill amount of 46
Delivering the order
Order with order id as Pizza-57 being delivered to John
Order is to be delivered to: Pune
```

我们有一个客户类，它有客户属性，如姓名、地址。订单类别包含所有订单信息，如项目名称、数量。

账单计算类计算总账单，并在订单对象中设置账单金额。交付应用程序有一项任务，即向客户交付订单。在现实世界中，这些类会更加复杂，可能需要将它们的功能进一步分解为多个类。

例如，账单计算逻辑可能需要实现某种查找功能，在这种功能中，我们根据某种数据库查找订单中包含的每个项目的价格，将它们相加，加上税费、送货费等，最后得出总价格。根据代码开始变得有多复杂，我们可能希望将税收、数据库查询等转移到其他单独的类中。类似地，交付类可能希望与另一个任务管理系统接口，该系统实际上根据位置、轮班时间、交付人员是否实际上班等将交付任务分配给不同的交付代理。当需要特殊处理时，这些单独的步骤可以转移到不同的类。

如果在同一个类中添加了账单计算和订单交付的功能，那么只要账单计算逻辑或交付代理逻辑需要更改，该类就会被修改；这违反了单一责任原则。根据这个例子，我们有一个单独的类来处理这些函数。理想情况下，任何单一的业务需求变更应该只对一个类别产生影响，从而符合单一责任原则。
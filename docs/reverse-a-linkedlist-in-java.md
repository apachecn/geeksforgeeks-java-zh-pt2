# 在 Java 中反向链接列表

> 原文:[https://www.geeksforgeeks.org/reverse-a-linkedlist-in-java/](https://www.geeksforgeeks.org/reverse-a-linkedlist-in-java/)

假设你已经在 java 中浏览过[链表](https://www.geeksforgeeks.org/linked-list-in-java/)并且知道链表。这篇文章包含了不同的例子来反转链表，如下所示:

**1。通过编写我们自己的函数(使用额外的空间):** reverseLinkedList()方法包含用于反转链表中字符串对象的逻辑。此方法将链表作为参数，以相反的顺序遍历所有元素，并将其添加到新创建的链表中。

**算法:**
第一步。用 n 个元素创建一个链表
步骤 2。创建一个空链表，用于存储反向元素
步骤 3。开始从“n”到“0”遍历列表，并将元素存储在新创建的列表中。
第四步。元素将按以下顺序存储:n，n-1，n-2，……0
步骤 5。将列表返回给呼叫者并打印出来

```
Example:
Step 1: LL: 1 -> 2 -> 3 -> 4 -> 5 where 'LL' is the linked list with n elements
Step 2: 'Rev' is an empty linked list
Step 3: Start traversing, the below passes are the intermediate steps while traversing
          1st pass: Rev: 5
          2nd pass: Rev: 5 -> 4
          3rd pass: Rev: 5 -> 4 -> 3
          4th pass: Rev: 5 -> 4 -> 3 -> 2
          5th pass: Rev: 5 -> 4 -> 3 -> 2 -> 1
Step 4: nth element of 'LL' is stored in 0th position of 'Rev', 
          n-1 element of LL is stored in 1st position of Rev and so on......
Step 5: Return Rev: 5 -> 4 -> 3 -> 2 -> 1  to the calling function.

```

```
// Java program for reversing linked list using additional space
import java.util.*;

public class LinkedListTest1 {
    public static void main(String[] args)
    {
        // Declaring linkedlist without any initial size
        LinkedList<String> linkedli = new LinkedList<String>();
        // Appending elements at the end of the list
        linkedli.add("Cherry");
        linkedli.add("Chennai");
        linkedli.add("Bullet");
        System.out.print("Elements before reversing: " + linkedli);
        linkedli = reverseLinkedList(linkedli);
        System.out.print("\nElements after reversing: " + linkedli);
    }

    // Takes a linkedlist as a parameter and returns a reversed linkedlist
    public static LinkedList<String> reverseLinkedList(LinkedList<String> llist)
    {
        LinkedList<String> revLinkedList = new LinkedList<String>();
        for (int i = llist.size() - 1; i >= 0; i--) {

            // Append the elements in reverse order
            revLinkedList.add(llist.get(i));
        }
        // Return the reversed arraylist
        return revLinkedList;
    }
}
```

**时间复杂度:**O(n)
T3】空间复杂度: O(n)

**注意:**由于我们使用额外的内存空间来存储所有反转的‘n’个元素，空间复杂度为 O(n)。

**Output:**

```
Elements before reversing: [Cherry, Chennai, Bullet]
Elements after reversing: [Bullet, Chennai, Cherry]

```

**2。通过编写我们自己的函数(不使用额外的空间):**在前面的例子中，链表额外用于存储所有占用更多空间的反向元素。为了避免这种情况，可以使用相同的链表进行反转。

**算法:**
1。用 n 个元素创建一个链表
1。循环运行 n/2 次，其中“n”是 linkedlist 中的元素数。
2。第一遍，交换第一个和第 n 个元素
3。在第二遍中，交换第二个和第(n-1)个元素，以此类推，直到到达链表的中间。
4。循环终止后返回链表。

```
Example:
Input: 1 -> 2 -> 3 -> 4 -> 5
1st pass: (swap first and nth element)
           5 -> 2 -> 3 -> 4 -> 1
2nd pass: (swap second and (n-1)th element)
           5 -> 4 -> 3 -> 2 -> 1
3rd pass: (reached mid, Terminate loop)
           5 -> 4 -> 3 -> 2 -> 1
Output: 5 -> 4 -> 3 -> 2 -> 1

```

```
// Java program for reversing an arraylist without
// using any additional space
import java.util.*;

public class LinkedListTest2 {
    public static void main(String[] args)
    {
        // Declaring linkedlist without any initial size
        LinkedList<Integer> linkedli = new LinkedList<Integer>();

        // Appending elements at the end of the list
        linkedli.add(new Integer(1));
        linkedli.add(new Integer(2));
        linkedli.add(new Integer(3));
        linkedli.add(new Integer(4));
        linkedli.add(new Integer(5));
        System.out.print("Elements before reversing: " + linkedli);

        // Calling user defined function for reversing
        linkedli = reverseLinkedList(linkedli);
        System.out.print("\nElements after reversing: " + linkedli);
    }

    // Takes a linkedlist as a parameter and returns a reversed linkedlist
    public static LinkedList<Integer> reverseLinkedList(LinkedList<Integer> llist)
    {
        for (int i = 0; i < llist.size() / 2; i++) {
            Integer temp = llist.get(i);
            llist.set(i, llist.get(llist.size() - i - 1));
            llist.set(llist.size() - i - 1, temp);
        }

        // Return the reversed arraylist
        return llist;
    }
}
```

**时间复杂度:**O(n/2)
T3】空间复杂度: O(1)

**Output:**

```
Elements before reversing: [1, 2, 3, 4, 5]
Elements after reversing: [5, 4, 3, 2, 1]

```

**3。通过使用 Collections 类:** Collections 是 java.util 包中的一个类，它包含各种静态方法，用于搜索、排序、反转、查找最大值、最小值等。我们可以使用内置的 Collections.reverse()方法来反转链表。它将一个列表作为输入参数，并返回反向列表。

**注意:Collections.reverse()方法使用的算法与“通过编写我们自己的函数(不使用额外的空间)”**相同

```
// Java program for reversing a linked list using
// In-built collections class
import java.util.*;

public class LinkedListTest3 {
    public static void main(String[] args)
    {
        // Declaring linkedlist without any initial size
        LinkedList<Integer> linkedli = new LinkedList<Integer>();

        // Appending elements at the end of the list
        linkedli.add(new Integer(1));
        linkedli.add(new Integer(2));
        linkedli.add(new Integer(3));
        linkedli.add(new Integer(4));
        linkedli.add(new Integer(5));
        System.out.print("Elements before reversing: " + linkedli);

        // Collections.reverse method takes a list as a
        // parameter and returns the reversed list
        Collections.reverse(linkedli);

        System.out.print("\nElements after reversing: " + linkedli);
    }
}
```

**时间复杂度:**O(n/2)
T3】空间复杂度: O(1)

**Output:**

```
Elements before reversing: [1, 2, 3, 4, 5]
Elements after reversing: [5, 4, 3, 2, 1]

```

**4。反转用户定义对象的链接列表:**创建一个雇员类，用于创建用户定义对象，其中雇员标识、雇员名称、部门名称作为类变量，在构造函数中初始化。将创建一个仅包含员工(用户定义)对象的链接列表。使用 add()方法将这些对象添加到链接列表中。使用集合类的内置反转()方法反转链表。

printElements()方法用于遍历链表中所有用户定义的对象，并打印每个对象的员工 ID、姓名和部门名称。

```
// Java program for reversing a inkedlist of user defined objects
import java.util.*;

class Employee {
    int empID;
    String empName;
    String deptName;

    // Constructor for initializing the class variables
    public Employee(int empID, String empName, String deptName)
    {
        this.empID = empID;
        this.empName = empName;
        this.deptName = deptName;
    }
}

public class LinkedListTest4 {
    public static void main(String[] args)
    {
        // Declaring linkedList without any initial size
        LinkedList<Employee> linkedli = new LinkedList<Employee>();

        // Creating user defined objects
        Employee emp1 = new Employee(123, "Cherry", "Fashionist");
        Employee emp2 = new Employee(124, "muppala", "Development");
        Employee emp3 = new Employee(125, "Bullet", "Police");

        // Appending all the objects to linkedList
        linkedli.add(emp1);
        linkedli.add(emp2);
        linkedli.add(emp3);
        System.out.print("Elements before reversing: ");
        printElements(linkedli);

        // Collections.reverse method takes a list as a parameter
        // and returns the reversed list
        Collections.reverse(linkedli);

        System.out.print("\nElements after reversing: ");
        printElements(linkedli);
    }

    // Iterate through all the elements and print
    public static void printElements(LinkedList<Employee> llist)
    {
        for (int i = 0; i < llist.size(); i++) {
            System.out.print("\n EmpID:" + llist.get(i).empID + ", EmpName:"
                             + llist.get(i).empName + ", Department:" + llist.get(i).deptName);
        }
    }
}
```

**时间复杂度:**O(n/2)
T3】空间复杂度: O(1)

**Output:**

```
Elements before reversing: 
 EmpID:123, EmpName:Cherry, Department:Fashionist
 EmpID:124, EmpName:muppala, Department:Development
 EmpID:125, EmpName:Bullet, Department:Police
Elements after reversing: 
 EmpID:125, EmpName:Bullet, Department:Police
 EmpID:124, EmpName:muppala, Department:Development
 EmpID:123, EmpName:Cherry, Department:Fashionist

```

请参见[反转链表](https://www.geeksforgeeks.org/reverse-a-linked-list/)以反转用户定义的链表。
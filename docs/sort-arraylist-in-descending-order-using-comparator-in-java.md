# 在 Java 中使用比较器对数组列表进行降序排序

> 原文:[https://www . geesforgeks . org/sort-ArrayList-按降序排列-使用 java 中的比较器/](https://www.geeksforgeeks.org/sort-arraylist-in-descending-order-using-comparator-in-java/)

比较器是一个接口，用于以排序的方式重新排列[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)。比较器用于对用户定义对象的数组列表进行排序。在 java 中，比较器是在 java.util 包中提供的。使用比较器根据多个变量对数组列表进行排序，或者简单地实现比较器，而不影响原始的用户定义类。若要使用比较器对数组列表进行排序，请重写比较器接口提供的 compare()方法。

覆盖 ***compare()方法*** ，使其按照降序而不是升序对数组列表重新排序。仅在比较部分按降序更改。查看两个 compare()函数的区别。

```java
Ascending Order
public int compare(Item i1, Item i2)
    {
        if (i1.Property== i2.Property)
            return 0;
        else if (s1.Property > s2.Property)
            return 1;
        else
            return -1;
    }

Descending Order
public int compare(Item i1, Item i2)
    {
        if (i1.Property== i2.Property)
            return 0;
        else if (s1.Property < s2.Property)
            return 1;
        else
            return -1;
    }
```

如果需要根据字符串类型的变量(如名称等)对数组列表重新排序。重写下面的 compare()函数 Like。

```java
Ascending Order
public int compare(Shop s1, Shop s2)
    {
        return s1.name.compareTo(s2.name);
    }

Descending Order
public int compare(Shop s1, Shop s2)
    {
        return s2.name.compareTo(s1.name);
    }
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to sort the ArrayList 
// in descending order using comparator
import java.util.*;

// create the Laptop class
class Laptop {
    int ModalNo;
    String name;
    int ram;
    Laptop(int ModalNo, String name, int ram)
    {
        this.ModalNo = ModalNo;
        this.name = name;
        this.ram = ram;
    }
}

// creates the comparator for comparing RAM
class RamComparator implements Comparator<Laptop> {
    // override the compare() method
    public int compare(Laptop l1, Laptop l2)
    {
        if (l1.ram == l2.ram) {
            return 0;
        }
        else if (l1.ram < l2.ram) {
            return 1;
        }
        else {
            return -1;
        }
    }
}

class GFG {
    public static void main(String[] args)
    {
        // create the ArrayList object
        ArrayList<Laptop> l = new ArrayList<Laptop>();
        l.add(new Laptop(322, "Dell", 2));
        l.add(new Laptop(342, "Asus", 8));
        l.add(new Laptop(821, "HP", 16));
        l.add(new Laptop(251, "Lenovo", 6));
        l.add(new Laptop(572, "Acer", 4));

        System.out.println("before sorting");
        System.out.println("Ram"
                           + " "
                           + "Name"
                           + " "
                           + "ModalNo");
        for (Laptop laptop : l) {
            System.out.println(laptop.ram + " "
                               + laptop.name + " "
                               + laptop.ModalNo);
        }
        System.out.println();

        System.out.println("After sorting(sorted by Ram)");
        System.out.println("Ram"
                           + " "
                           + "Name"
                           + " "
                           + "ModalNo");

        // call the sort function
        Collections.sort(l, new RamComparator());
        for (Laptop laptop : l) {
            System.out.println(laptop.ram + " "
                               + laptop.name + " "
                               + laptop.ModalNo);
        }
    }
}
```

**Output**

```java
before sorting
Ram Name ModalNo
2 Dell 322
8 Asus 342
16 HP 821
6 Lenovo 251
4 Acer 572

After sorting(sorted by Ram)
Ram Name ModalNo
16 HP 821
8 Asus 342
6 Lenovo 251
4 Acer 572
2 Dell 322
```
# 简单绑定用示例将()方法放入 Java 中

> 原文:[https://www . geesforgeks . org/simplebindings-plat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplebindings-put-method-in-java-with-examples/)

**简单绑定类**的 **put()** 方法用于在简单绑定对象中添加指定的键和值对。键和值都作为参数传递。该键被重命名为要在 SimpleBindings 对象中设置的值的名称。设置值后，方法返回指定键的前一个值，如果该键以前未设置，它将返回 null。
**语法:**

```
public Object put(String name, Object value)
```

**参数:**该方法接受两个参数:

*   **名称**是值的名称，并且
*   **值**，即要设置的值。

**返回值:**该方法返回指定键的**先前值**，如果该键先前未设置，则返回**空值**。
**异常:**该方法抛出以下异常:

*   **空指针异常**:如果指定名称为空
*   **IllegalArgumentException** :如果指定的名称为空字符串

Java 程序演示 put()方法的工作原理:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate get() method

import javax.script.SimpleBindings;

public class GFG {
    public static void main(String[] args)
    {

        // Create simpleBindings object
        SimpleBindings bindings
            = new SimpleBindings();

        // Add key value pair using put()
        bindings.put("key1", "value1");
        bindings.put("key2", "value2");
        bindings.put("key3", "value3");

        // Print them
        System.out.println("Key1: "
                           + bindings.get("key1"));
        System.out.println("Key2: "
                           + bindings.get("key2"));
        System.out.println("Key3: "
                           + bindings.get("key3"));
    }
}
```

**Output:** 

```
Key1: value1
Key2: value2
Key3: value3
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate get() method

import javax.script.SimpleBindings;

public class GFG {
    public static void main(String[] args)
    {

        // Create simpleBindings object
        SimpleBindings asiaTeamList
            = new SimpleBindings();

        // Add team in asiaTeamList using put()
        asiaTeamList.put("team1", "India");
        asiaTeamList.put("team2", "Sri Lanka");
        asiaTeamList.put("team3", "Pakistan");
        asiaTeamList.put("team4", "Bangladesh");

        // Print
        System.out.println(
            asiaTeamList.get("team1"));
        System.out.println(
            asiaTeamList.get("team2"));
        System.out.println(
            asiaTeamList.get("team3"));
        System.out.println(
            asiaTeamList.get("team4"));
    }
}
```

**Output:** 

```
India
Sri Lanka
Pakistan
Bangladesh
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplebindings . html # put(Java . lang . string，java.lang.Object)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleBindings.html#put(java.lang.String, java.lang.Object))
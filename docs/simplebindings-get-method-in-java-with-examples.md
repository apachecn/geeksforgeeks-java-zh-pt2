# Java 中的 SimpleBindings get()方法，示例

> 原文:[https://www . geesforgeks . org/simplebindings-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplebindings-get-method-in-java-with-examples/)

**简单绑定类**的 **get()** 方法用于返回这个简单绑定对象将作为参数传递的键映射到的值。

**语法:**

```
public Object get(Object key)

```

**参数:**该方法只接受一个参数**键**，该键的关联值将被返回。

**返回值:**该方法返回该键映射到的值，或者为空。

**异常:**该方法抛出以下异常:

*   null 指针异常:唉呀关键点吾曰空值
*   **类种姓例外**:如果键不是线
*   **非法引数异常**:关键子串

Java 程序演示 get()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate get() method

import javax.script.SimpleBindings;

public class GFG {
    public static void main(String[] args)
    {

        // create simpleBindings object
        SimpleBindings bindings
            = new SimpleBindings();

        // add some keys with values
        bindings.put("key1", "value1");
        bindings.put("key2", "value2");
        bindings.put("key3", "value3");

        // get value of key3
        Object value = bindings.get("key3");

        // print
        System.out.println("key3 value: "
                           + value);
    }
}
```

**输出:**

```
key3 value: value3

```

**程序二:**

```
// Java program to demonstrate get() method

import javax.script.SimpleBindings;

public class GFG {
    public static void main(String[] args)
    {

        // create simpleBindings object
        SimpleBindings asiaTeamList
            = new SimpleBindings();

        // add team in asiaTeamList
        asiaTeamList.put("team1", "India");
        asiaTeamList.put("team2", "Sri Lanka");
        asiaTeamList.put("team3", "Pakistan");
        asiaTeamList.put("team4", "Bangladesh");

        // get team1, team2 and team5 values
        Object team1 = asiaTeamList.get("team1");
        Object team2 = asiaTeamList.get("team2");
        Object team5 = asiaTeamList.get("team5");

        // print team names
        System.out.println("Team1 :"
                           + team1);
        System.out.println("Team2 :"
                           + team2);
        System.out.println("Team5 :"
                           + team5);
    }
}
```

**输出:**

```
Team1 :India
Team2 :Sri Lanka
Team5 :null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplebindings . html # get(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleBindings.html#get(java.lang.Object))
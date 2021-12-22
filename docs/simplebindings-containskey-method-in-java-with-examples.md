# 简单绑定包含 Java 中的 Key()方法，示例

> 原文:[https://www . geesforgeks . org/simplebindings-contains key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplebindings-containskey-method-in-java-with-examples/)

如果支持此简单绑定对象的映射包含指定键的映射，则使用**简单绑定类**的 **containsKey()** 方法返回 true。如果 SimpleBindings 对象包含该键，则该方法返回 true 否则返回 false。

**语法:**

```
public boolean containsKey(Object key)

```

**参数:**该方法只接受一个参数**键**，该键在该地图中的存在性有待检验。

**返回值:**如果该映射包含指定键的映射，则该方法返回真。

**异常:**该方法抛出以下异常:

*   null 指针异常:唉呀关键点吾曰空值
*   **类种姓例外**:如果键不是线
*   **非法引数异常**:关键子串

演示 containsKey()方法工作原理的 Java 程序:

**程序 1:**

```
// Java program to demonstrate containsKey() method

import javax.script.SimpleBindings;

public class GFG {
    public static void main(String[] args)
    {

        // create simpleBindings object
        SimpleBindings bindings = new SimpleBindings();

        // add some keys with values
        bindings.put("key1", "value1");
        bindings.put("key2", "value2");
        bindings.put("key3", "value3");

        // check key2 is exists in bindings or not
        boolean isKey2Exist = bindings.containsKey("key2");

        // print
        System.out.println("Key2 exits:" + isKey2Exist);
    }
}
```

**输出:**

```
Key2 exits:true

```

**程序二:**

```
// Java program to demonstrate containsKey() method

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

        // check England exists in bindings or not
        boolean isKey2Exist
            = asiaTeamList.containsKey("England");

        // print
        System.out.println("England exits in Asia Team:"
                           + isKey2Exist);
    }
}
```

**输出:**

```
England exits in Asia Team:false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplebindings . html # contains key(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleBindings.html#containsKey(java.lang.Object))
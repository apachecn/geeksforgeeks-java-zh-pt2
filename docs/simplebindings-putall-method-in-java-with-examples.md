# Java 中的 SimpleBindings putAll()方法，带示例

> 原文:[https://www . geesforgeks . org/simplebindings-pull-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplebindings-putall-method-in-java-with-examples/)

**简单绑定类**的 **putAll()** 方法用于添加映射的所有键值对，这些键值对作为参数传递给简单绑定对象。

**语法:**

```java
public void putAll(Map<String, Object> toMerge)
```

**参数:**该方法接受参数**为要添加的值的映射**。
**返回值:**此方法不返回任何内容。
**异常:**该方法抛出以下异常:

*   **NullPointRexception**:如果一个大型映射为空或者如果映射中的某个键为空。
*   **IllegalArgumentException** :如果地图中的某个键是空字符串。

以下是演示 putAll()方法工作的程序:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java programs to Illustrate
// the working of putAll() method

import javax.script.SimpleBindings;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create simpleBindings object
        SimpleBindings bindings = new SimpleBindings();

        // create Map
        HashMap<String, String> map = new HashMap<>();

        // add key value pair to Map
        map.put("key1", "value1");
        map.put("key2", "value2");
        map.put("key3", "value3");

        // apply putAll
        bindings.putAll(map);

        // print
        System.out.println(
            "Key1:"
            + bindings.get("key1"));
        System.out.println(
            "Key2:"
            + bindings.get("key2"));
        System.out.println(
            "Key3:"
            + bindings.get("key3"));
    }
}
```

**Output:** 

```java
Key1:value1
Key2:value2
Key3:value3
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java programs to Illustrate
// the working of putAll() method

import javax.script.SimpleBindings;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create simpleBindings object
        SimpleBindings asiaTeamList
            = new SimpleBindings();

        // create Map
        HashMap<String, String> map = new HashMap<>();

        // add team in map using put()
        map.put("team1", "India");
        map.put("team2", "Sri Lanka");
        map.put("team3", "Pakistan");
        map.put("team4", "Bangladesh");

        // apply putAll
        asiaTeamList.putAll(map);

        // print
        System.out.println(
            "Team1: "
            + asiaTeamList.get("team1"));
        System.out.println(
            "Team2: "
            + asiaTeamList.get("team2"));
        System.out.println(
            "Team3: "
            + asiaTeamList.get("team3"));
        System.out.println(
            "Team4: "
            + asiaTeamList.get("team4"));
    }
}
```

**Output:** 

```java
Team1: India
Team2: Sri Lanka
Team3: Pakistan
Team4: Bangladesh
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplebindings . html # putAll(Java . util . map)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleBindings.html#putAll(java.util.Map))
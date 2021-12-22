# Java 中的 SimpleBindings remove()方法，示例

> 原文:[https://www . geesforgeks . org/simplebindings-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplebindings-remove-method-in-java-with-examples/)

**简单绑定类**的 **remove()** 方法用于从该简单绑定对象中移除该键的映射(如果存在)。此方法返回与指定键关联的前一个值，如果没有键映射，则返回 null。
**语法:**

```
public Object remove(Object key)
```

**参数:**该方法接受一个参数**键**，该键的映射将从地图中移除。
**返回值:**此方法返回与指定键关联的前一个值，如果没有键映射，则返回 null。
**异常:**此方法抛出以下异常:

*   **NullPointRexception**:如果键为空。
*   **ClassCastException** :如果键不是 String。
*   **IllegalArgumentException** :如果键为空字符串。

以下是说明 remove()方法工作的程序:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java programs to Illustrate
// the working of remove() method

import javax.script.SimpleBindings;

public class GFG {
    public static void main(String[] args)
    {

        // create simpleBindings object
        SimpleBindings bindings = new SimpleBindings();

        // add key value pair using remove()
        bindings.put("key1", "value1");
        bindings.put("key2", "value2");
        bindings.put("key3", "value3");

        // print before removing key1 and key2
        System.out.println("before removing key1 and key2");
        System.out.println("Key1: " + bindings.get("key1"));
        System.out.println("Key2: " + bindings.get("key2"));
        System.out.println("Key3: " + bindings.get("key3"));

        // remove key1 and key2
        bindings.remove("key1");
        bindings.remove("key2");

        // print after removing key1 and key2
        System.out.println("after removing key1 and key2");
        System.out.println("Key1: " + bindings.get("key1"));
        System.out.println("Key2: " + bindings.get("key2"));
        System.out.println("Key3: " + bindings.get("key3"));
    }
}
```

**Output: **

```
before removing key1 and key2
Key1: value1
Key2: value2
Key3: value3
after removing key1 and key2
Key1: null
Key2: null
Key3: value3
```
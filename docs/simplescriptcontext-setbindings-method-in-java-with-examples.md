# Java 中的 SimpleScriptContext setBindings()方法，带示例

> 原文:[https://www . geesforgeks . org/simplescriptcontext-set bindings-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplescriptcontext-setbindings-method-in-java-with-examples/)

SimpleScriptContext 类的 **setBindings()** 方法用于为给定的作用域设置属性绑定，其中绑定和作用域作为参数传递给该方法。如果作用域是 ENGINE_SCOPE，给定的绑定将替换 engineScope 字段。如果作用域是全局作用域，给定的绑定将替换全局作用域字段。

**语法:**

```
public void setBindings(Bindings bindings,
                        int scope)

```

**参数:**该方法接受两个参数:

*   **绑定**是要设置和的属性的绑定
*   **范围**是设置属性的范围。

**返回值:**此方法不返回任何内容。

**异常:**该方法抛出以下异常:

*   **NullPointerException** :如果作用域的值为 ENGINE_SCOPE，指定的 Bindings 为空。
*   **IllegalArgumentException** :如果作用域无效。

下面的程序说明了 simplescriptcontext . setbindings()方法:
**程序 1:**

```
// Java program to demonstrate
// SimpleScriptContext.setBindings() method

import javax.script.ScriptContext;
import javax.script.SimpleBindings;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // create Bindings
        SimpleBindings bindings
            = new SimpleBindings();

        // add some key-value to bindings
        bindings.put("name1", "Value1");

        // add bindings to SimpleScriptContext using
        // setBindings() Method
        simple.setBindings(
            bindings,
            ScriptContext.ENGINE_SCOPE);

        // print
        System.out.println(
            "name1:"
            + simple.getAttribute("name1"));
    }
}
```

**Output:**

```
name1:Value1

```

**程序 2:**

```
// Java program to demonstrate
// SimpleScriptContext.setBindings() method

import javax.script.ScriptContext;
import javax.script.SimpleBindings;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // create Bindings
        SimpleBindings bindings
            = new SimpleBindings();

        // add some key-value to bindings
        bindings.put("Team1", "India");
        bindings.put("Team2", "Japan");
        bindings.put("Team3", "Nepal");

        // add bindings to SimpleScriptContext using
        // setBindings() Method
        simple.setBindings(
            bindings,
            ScriptContext.ENGINE_SCOPE);

        // print
        System.out.println("Team1:"
                           + simple.getAttribute("Team1"));
        System.out.println("Team2:"
                           + simple.getAttribute("Team2"));
        System.out.println("Team3:"
                           + simple.getAttribute("Team3"));
    }
}
```

**Output:**

```
Team1:India
Team2:Japan
Team3:Nepal

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplescriptcontext . html # setBindings(javax . script . bindings，int)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleScriptContext.html#setBindings(javax.script.Bindings, int))
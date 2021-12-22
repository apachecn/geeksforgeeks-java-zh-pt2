# Java 中的 SimpleScriptContext getBindings()方法，带示例

> 原文:[https://www . geesforgeks . org/simplescriptcontext-get bindings-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplescriptcontext-getbindings-method-in-java-with-examples/)

SimpleScriptContext 类的 **getBindings()** 方法用于返回与这个 ScriptContext 中的给定范围相关联的绑定，其中范围作为参数传递。

**语法:**

```
Bindings getBindings(int scope)

```

**参数:**该方法接受单个参数**范围**，这是本脚本上下文中的范围。

**返回值:**此方法返回关联的绑定，如果尚未设置，则返回空值。

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException** :如果在这种类型的脚本上下文中没有为指定的作用域值定义绑定。

下面的程序说明了 simplescriptcontext . getbindings()方法:
**程序 1:**

```
// Java program to demonstrate
// SimpleScriptContext.getBindings() method

import javax.script.Bindings;
import javax.script.ScriptContext;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // add some attribute
        simple.setAttribute(
            "name1",
            "Value1",
            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute(
            "name2",
            "Value2",
            ScriptContext.ENGINE_SCOPE);

        // get bindings using getBindings()
        Bindings bindings
            = simple.getBindings(
                ScriptContext.ENGINE_SCOPE);

        // print
        System.out.println("Bindings value for name1:"
                           + bindings.get("name1"));
        System.out.println("Bindings value for name2:"
                           + bindings.get("name2"));
    }
}
```

**Output:**

```
Bindings value for name1:Value1
Bindings value for name2:Value2

```

**程序 2:**

```
// Java program to demonstrate
// SimpleScriptContext.getBindings() method

import javax.script.Bindings;
import javax.script.ScriptContext;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // add some attribute
        simple.setAttribute(
            "Team1",
            "India",
            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute(
            "Team2",
            "Japan",
            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute(
            "Team3",
            "Nepal",
            ScriptContext.ENGINE_SCOPE);

        // get bindings using getBindings()
        Bindings bindings
            = simple.getBindings(
                ScriptContext.ENGINE_SCOPE);

        // print
        System.out.println("Bindings value for Team1:"
                           + bindings.get("Team1"));
        System.out.println("Bindings value for Team2:"
                           + bindings.get("Team2"));
        System.out.println("Bindings value for Team3:"
                           + bindings.get("Team3"));
    }
}
```

**Output:**

```
Bindings value for Team1:India
Bindings value for Team2:Japan
Bindings value for Team3:Nepal

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/script/script context . html # getBindings(int)](https://docs.oracle.com/javase/10/docs/api/javax/script/ScriptContext.html#getBindings(int))
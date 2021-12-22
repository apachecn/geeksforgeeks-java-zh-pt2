# Java 中的 SimpleScriptContext getattributescope()方法，示例

> 原文:[https://www . geesforgeks . org/simplescriptcontext-getattributesscope-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplescriptcontext-getattributesscope-method-in-java-with-examples/)

SimpleScriptContext 类的**getattributessscope()**方法用于返回定义属性的范围，属性的名称作为参数传递。

**语法:**

```
public int getAttributesScope(String name)

```

**参数:**此方法接受单个参数**名称**，这是属性的名称。

**返回值:**如果在任何范围内都没有定义给定名称的属性，则该方法返回最低范围并返回-1。

**异常:**该方法抛出以下异常:

*   如果名称为空，则**为空指针异常**。
*   如果名称为空，则出现 **IllegalArgumentException** 。

下面的程序说明了 simplescriptcontext . getattributesscope()方法:
**程序 1:**

```
// Java program to demonstrate
// SimpleScriptContext.getAttributesScope() method

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
            "name",
            "Value",
            ScriptContext.ENGINE_SCOPE);

        // get scope using getAttributesScope()
        int scope = simple.getAttributesScope("name");

        // print
        System.out.println("Scope :" + scope);
    }
}
```

**Output:**

```
Scope :100

```

**程序 2:**

```
// Java program to demonstrate
// SimpleScriptContext.getAttributesScope() method

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
            ScriptContext.GLOBAL_SCOPE);
        simple.setAttribute(
            "Team3",
            "Nepal",
            ScriptContext.GLOBAL_SCOPE);

        // get scope using getAttributesScope()
        int scope1
            = simple.getAttributesScope("Team1");
        int scope2
            = simple.getAttributesScope("Team2");
        int scope3
            = simple.getAttributesScope("Team3");

        // print scopes of different teams
        System.out.println("Scope for Team1: "
                           + scope1);
        System.out.println("Scope for Team2: "
                           + scope2);
        System.out.println("Scope for Team3: "
                           + scope3);
    }
}
```

**Output:**

```
Scope for Team1: 100
Scope for Team2: -1
Scope for Team3: -1

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/script/script context . html](https://docs.oracle.com/javase/10/docs/api/javax/script/ScriptContext.html)
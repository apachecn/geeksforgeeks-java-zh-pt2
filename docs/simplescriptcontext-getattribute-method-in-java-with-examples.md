# Java 中的 SimpleScriptContext getAttribute()方法，示例

> 原文:[https://www . geesforgeks . org/simplescriptcontext-getattribute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplescriptcontext-getattribute-method-in-java-with-examples/)

SimpleScriptContext 类的 **getAttribute()** 方法用于返回给定名称的属性值作为该方法的参数。通过属性名搜索值在搜索顺序中最早出现的范围内。

**语法:**

```
public Object getAttribute(String name)

```

**参数:**此方法接受单个参数**名称**，这是要检索的属性的名称。

**返回值:**该方法返回定义了给定名称的属性的最低范围内的属性的值，如果在任何范围内都不存在该名称的属性，则返回 null。

**异常:**该方法抛出以下异常:

*   **NullPointRexception**:如果名称为空。
*   **IllegalArgumentException** :如果名称为空。

下面的程序说明了 simplescriptcontext . getattribute()方法:
**程序 1:**

```
// Java program to demonstrate
// SimpleScriptContext.getAttribute() method

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

        // get value using getAttribute()
        Object value
            = simple.getAttribute("name");

        // print
        System.out.println(value);
    }
}
```

**Output:**

```
Value

```

**程序 2:**

```
// Java program to demonstrate
// SimpleScriptContext.getAttribute() method

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

        // get value using getAttribute()
        Object value1
            = simple.getAttribute("Team1");
        Object value2
            = simple.getAttribute("Team2");
        Object value3
            = simple.getAttribute("Team3");

        // print
        System.out.println(value1);
        System.out.println(value2);
        System.out.println(value3);
    }
}
```

**Output:**

```
India
Japan
Nepal

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplescriptcontext . html # GetAttribute(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleScriptContext.html#getAttribute(java.lang.String))
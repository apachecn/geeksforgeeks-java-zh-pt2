# Java 中的 SimpleScriptContext setAttribute()方法，带示例

> 原文:[https://www . geesforgeks . org/simplescriptcontext-set attribute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplescriptcontext-setattribute-method-in-java-with-examples/)

SimpleScriptContext 类的 **setAttribute()** 方法用于在给定范围内设置属性的值，其中属性的名称、属性值和属性的范围作为参数传递。如果作用域是全局作用域，并且没有为全局作用域设置绑定，那么 setAttribute 调用就是无操作

**语法:**

```
public void setAttribute(String name,
       Object value, int scope)

```

**参数:**该方法接受三个参数:

*   **名称**是要设置的属性的名称，
*   **值**是属性和的值
*   **范围**是设置属性的范围。

**返回值:**此方法不返回任何内容。

**异常:**该方法抛出以下异常:

*   **NullPointRexception**:如果名称为空。
*   **IllegalArgumentException** :如果名称为空或者范围无效。

下面的程序说明了 simplescriptcontext . setattribute()方法:
**程序 1:**

```
// Java program to demonstrate
// SimpleScriptContext.setAttribute() method

import javax.script.ScriptContext;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // add some attribute using setAttribute()
        simple.setAttribute(
            "name1", "Value1",
            ScriptContext.ENGINE_SCOPE);

        // print
        System.out.println("name1:"
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
// SimpleScriptContext.setAttribute() method

import javax.script.ScriptContext;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // add some attribute using setAttribute()
        simple.setAttribute("Team1", "India",
                            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute("Team2", "Japan",
                            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute("Team3", "Nepal",
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

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplescriptcontext . html # setAttribute(Java . lang . string，java.lang.Object，int)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleScriptContext.html#setAttribute(java.lang.String, java.lang.Object, int))
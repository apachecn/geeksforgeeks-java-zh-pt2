# Java 中的定时器取消()方法，示例

> 原文:[https://www . geesforgeks . org/timer-cancel-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timer-cancel-method-in-java-with-examples/)

**定时器类**的 **cancel()** 方法用于终止该定时器并移除任何当前计划的任务。

**语法:**

```
public void cancel()

```

**参数:**函数不接受任何参数。

**返回值:**该方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.Timer.cancel()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // creating timertask, timer
        Timer timer = new Timer();
        TimerTask tt = new TimerTask() {

            public void run()
            {
                for (int i = 1; i <= 15; i++) {
                    System.out.println("working on the task");
                    if (i >= 7) {
                        System.out.println("stop the task");
                        // loop stops after 7 iterations
                        timer.cancel();
                        break;
                    }
                }
            };
        };
        timer.schedule(tt, 1000, 1000);
    }
}
```

**Output:**

```
working on the task
working on the task
working on the task
working on the task
working on the task
working on the task
working on the task
stop the task

```

**程序 2:**

```
// program to demonstrate the
// function java.util.Timer.cancel()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // creating timertask, timer
        Timer timer = new Timer();
        TimerTask tt = new TimerTask() {

            public void run()
            {
                for (int i = 1; i <= 15; i++) {
                    System.out.println("working on the task");
                    if (i >= 7) {
                        System.out.println("stop the task");
                        // loop stops after 7 iterations
                        timer.cancel();
                    }
                }
            };
        };
        timer.schedule(tt, 1000, 1000);
    }
}
```

**Output:**

```
working on the task
working on the task
working on the task
working on the task
working on the task
working on the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task
working on the task
stop the task

```
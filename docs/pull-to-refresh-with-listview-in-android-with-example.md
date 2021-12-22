# 在安卓中用列表视图拉刷新，示例

> 原文:[https://www . geeksforgeeks . org/带示例的安卓拉取刷新列表视图/](https://www.geeksforgeeks.org/pull-to-refresh-with-listview-in-android-with-example/)

swipereffreshlayout[小部件](https://www.geeksforgeeks.org/components-android-application/)用于实现一种滑动刷新的用户界面设计模式。它使用垂直滑动手势来刷新视图内容。SwipeRefreshLayout 小部件检测垂直滑动并显示不同的进度条，并触发应用程序中的回调方法。要使用此行为，SwipeRefreshLayout 小部件必须是[列表视图](https://www.geeksforgeeks.org/android-listview-in-java-with-example/)或[网格视图](https://www.geeksforgeeks.org/gridview-using-baseadapter-in-android-with-example/)的父级。SwipeRefreshLayout 小部件的这种行为允许用户手动刷新布局。SwipeRefreshLayout 类包含一个名为**onrelfreshlistener**的侦听器。想要使用这个监听器的类应该实现 **SwipeRefreshLayout。onrelfreshlistener**界面。在垂直向下滑动手势时，该监听器被触发，并调用 **onRefresh()** 方法，可根据需要进行覆盖。

> 滑动刷新列表视图非常类似于滑动刷新回收视图。代替列表视图，我们使用回收视图。请参考[在安卓中用回收视图拉刷新，示例](https://www.geeksforgeeks.org/pull-to-refresh-with-recyclerview-in-android-with-example/)。

### **例**

在这个例子中，我们将字符串类型的数据存储到[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中，该列表用于填充列表视图。每当调用 **OnRefresh()** 方法时，数组列表数据都会被打乱。下面给出了一个示例 GIF，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

![Pull to Refresh with ListView in Android](img/b2d70c502f01942341372f287aaa9806.png)

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖关系**

我们正在使用 SwipeRefreshLayout。因此，我们需要为它添加依赖项。要添加依赖项，请转到**渐变脚本>构建.渐变(模块:应用)**并添加以下依赖项。添加依赖项后，您需要点击**立即同步**。

> 依赖项{
> 
> 实现“androidx . swiperefershlayout:swiperefershlayout:1 . 1 . 0”
> 
> }

在进一步移动之前，让我们添加一些颜色属性，以增强应用程序栏。转到**应用程序> res >值> colors.xml** 并添加以下颜色属性。

## 可扩展标记语言

```java
<resources> 
    <color name="colorPrimary">#0F9D58</color> 
    <color name="colorPrimaryDark">#16E37F</color> 
    <color name="colorAccent">#03DAC5</color> 
</resources> 
```

**步骤 3:使用 activity_main.xml 文件**

在这一步中，我们将创建 SwipeRefreshLayout 并向其中添加 ListView。转到 **app > res >布局> activity_main.xml** 并添加以下代码片段。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.swiperefreshlayout.widget.SwipeRefreshLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/swipeRefreshLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--ListView to store list items-->
    <ListView
        android:id="@+id/listView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</androidx.swiperefreshlayout.widget.SwipeRefreshLayout>
```

**步骤 4:使用 MainActivity.java 文件**

在这一步中，我们得到了 SwipeRefreshLayout 和 ListView 的引用，这是我们在**activity _ main . XML**布局文件中定义的。我们将创建一个字符串元素的数组列表，并实现[数组适配器](https://www.geeksforgeeks.org/arrayadapter-in-android-with-example/)，以便将数据设置到列表中。然后，我们在 **SwipeRefreshLayout** 上实现**setonrefreslistener**事件，调用 **OnRefresh()** 方法对列表元素进行洗牌。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import androidx.appcompat.app.AppCompatActivity;
import androidx.swiperefreshlayout.widget.SwipeRefreshLayout;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.Random;

public class MainActivity extends AppCompatActivity {

    SwipeRefreshLayout swipeRefreshLayout;
    ListView listView;
    ArrayList<String> arrayList = new ArrayList<>(Arrays.asList("C-Language", "Java", "Data Structure",
            "Networking", "Operating System", "Compiler Design", "Theory Of Computation",
            "Software Engineering", "Web Engineering"));

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Getting the reference of SwipeRefreshLayout and ListView
        swipeRefreshLayout = (SwipeRefreshLayout) findViewById(R.id.swipeRefreshLayout);
        listView = (ListView) findViewById(R.id.listView);

        // simple_list_item_1 is a built in layout. It is part of Android OS, instead of creating our own
        // xml layout we are using built-in layout
        ArrayAdapter arrayAdapter = new ArrayAdapter(this, android.R.layout.simple_list_item_1, arrayList);
        listView.setAdapter(arrayAdapter);

        // Implementing setOnRefreshListener on SwipeRefreshLayout
        swipeRefreshLayout.setOnRefreshListener(new SwipeRefreshLayout.OnRefreshListener() {
            @Override
            public void onRefresh() {
                swipeRefreshLayout.setRefreshing(false);
                // User defined method to shuffle the array list items
                shuffleListItems();
            }
        });
    }

    public void shuffleListItems() {
        // Shuffling the arraylist items on the basis of system time
        Collections.shuffle(arrayList, new Random(System.currentTimeMillis()));
        ArrayAdapter arrayAdapter = new ArrayAdapter(this, android.R.layout.simple_list_item_1, arrayList);
        listView.setAdapter(arrayAdapter);
    }
}
```

### **输出:在仿真器上运行**

<video class="wp-video-shortcode" id="video-513630-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201115111138/Pull-to-Refresh-with-ListView.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201115111138/Pull-to-Refresh-with-ListView.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201115111138/Pull-to-Refresh-with-ListView.mp4)</video>
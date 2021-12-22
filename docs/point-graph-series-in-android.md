# 安卓中的点图系列

> 原文:[https://www . geesforgeks . org/point-graph-in-series-in-Android/](https://www.geeksforgeeks.org/point-graph-series-in-android/)

我们已经看到在 Android 中使用[简单线图](https://www.geeksforgeeks.org/line-graph-view-in-android-with-example/)和[条形图](https://www.geeksforgeeks.org/how-to-create-a-barchart-in-android/)实现以图形格式表示数据。表示数据的另一种图形格式是点图系列。在本文中，我们将看看点图系列在安卓系统中的实现。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在这个应用程序中，我们将在安卓系统中以点图的方式显示样本数据。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-553314-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210127162950/Screenrecorder-2021-01-27-16-28-54-384.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210127162950/Screenrecorder-2021-01-27-16-28-54-384.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210127162950/Screenrecorder-2021-01-27-16-28-54-384.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖项进行构建. gradle(模块:app)**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com.jjoe64:graphview:4.2.2 '

添加了上面的依赖项后，现在同步您的项目，我们现在将转向 GraphView 的实现。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--graph view to display our graph-->
    <com.jjoe64.graphview.GraphView
        android:id="@+id/idGraphView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</LinearLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

import com.jjoe64.graphview.GraphView;
import com.jjoe64.graphview.series.DataPoint;
import com.jjoe64.graphview.series.PointsGraphSeries;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variable for graph view.
        GraphView graphView = findViewById(R.id.idGraphView);

        // on below line we are creating a new data
        // point series for our point graph series.
        // we are calling get data point method to add 
        // data point to our point graph series.
        PointsGraphSeries<DataPoint> series = new PointsGraphSeries<>(getDataPoint());

        // below line is to add series
        // to our graph view.
        graphView.addSeries(series);

        // below line is to activate
        // horizontal scrolling.
        graphView.getViewport().setScrollable(true);

        // below line is to activate horizontal 
        // zooming and scrolling.
        graphView.getViewport().setScalable(true);

        // below line is to activate vertical and 
        // horizontal zoom with scrolling.
        graphView.getViewport().setScalableY(true);

        // below line is to activate vertical scrolling.
        graphView.getViewport().setScrollableY(true);

        // below line is to set shape 
        // for the point of graph view.
        series.setShape(PointsGraphSeries.Shape.TRIANGLE);

        // below line is to set 
        // the size of our shape.
        series.setSize(12);

        // below line is to add color 
        // to our shape of graph view.
        series.setColor(R.color.purple_200);
    }

    private DataPoint[] getDataPoint() {
        // creating a variable for data point.
        DataPoint[] dataPoints = new DataPoint[]
                {
                        // on below line we are adding a new
                        // data point to our Data Point class.
                        new DataPoint(0, 1),
                        new DataPoint(1, 2),
                        new DataPoint(2, 3),
                        new DataPoint(3, 5),
                        new DataPoint(4, 1),
                        new DataPoint(4, 3),
                        new DataPoint(5, 3),
                        new DataPoint(6, 2)
                };
        // at last we are returning
        // the data point class.
        return dataPoints;
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-553314-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210127162950/Screenrecorder-2021-01-27-16-28-54-384.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210127162950/Screenrecorder-2021-01-27-16-28-54-384.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210127162950/Screenrecorder-2021-01-27-16-28-54-384.mp4)</video>
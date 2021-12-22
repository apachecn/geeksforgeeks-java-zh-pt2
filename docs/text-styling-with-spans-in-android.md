# 安卓中带跨度的文本样式

> 原文:[https://www . geesforgeks . org/text-styling-with-spans-in-Android/](https://www.geeksforgeeks.org/text-styling-with-spans-in-android/)

**跨度**是标记对象。这些可用于在字符或段落级别设置文本的样式。跨度附加在文本对象上，为我们提供了各种文本选项，包括为文本添加颜色、对文本应用可点击行为、缩放文本大小以及以自定义方式绘制文本。跨度还可以用于更改文本绘制属性、在画布上绘制，甚至更改文本布局。为了使用跨度，我们必须使用下面列出的一个类。

<figure class="table">

| 

类

 | 

可变文本

 | 

可变标记

 | 

数据结构

 |
| --- | --- | --- | --- |
| 跨越字符串 | 不 | 不 | Linear array |

</figure>

所有这些类都扩展了**跨区**界面。 **SpannableString** 和 **SpannableStringBuilder** 也扩展了 **Spannable** 界面。为了使用跨度，我们需要在**可展**对象上调用**设置跨度(对象跨度，int 开始，int 结束，int 标志)**。对象跨度参数是指应用于文本的跨度，开始和结束是指要应用跨度的文本位置的索引。

在应用跨度时，如果插入的文本在跨度边界内，则跨度会自动展开插入的文本。如果插入的文本位于起始索引和结束索引之间，则 flag 参数将决定跨度应包括还是排除插入的文本。

*   **可展开。SPAN _ EXCLUSIVE _ INCLUSIVE**–包括插入的文本
*   **可展开。SPAN _ EXCLUSIVE _ EXCLUSIVE**–排除插入的文本。

## **例**

在本例中，我们将通过使用 SpannableString 类以及 StyleSpan、下划线 Span 和删除线 Span 来更改文本的样式。下面给出了一个示例图像，以了解本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![Text Styling With Spans In Android Sample Image](img/e2d431682e67304da6cb75148d8b4a37.png)

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

在布局文件中，我们将有一个[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)。我们将使用跨度来设置文本的样式。下面是 activity_main.xml 文件的代码片段。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--The text we provide here is only
        for reference purpose we need to
        provide it in MainActivity.java file-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="I want Red and Green to be 
                      coloured and this to be Bold,
                      Italic and Underline and Strike-through"
        android:textAlignment="center"
        android:textSize="18sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**第三步:与 MainActivity.java 合作**

在**MainActivity.java**文件中，我们将首先定义一个需要设置样式的字符串。一旦我们定义了字符串，我们就将其转换为可展字符串，然后我们定义了需要修改的所有跨度，然后我们在可展字符串上设置这些跨度，最后将可展字符串设置为文本视图。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.graphics.Color;
import android.graphics.Typeface;
import android.os.Bundle;
import android.text.SpannableString;
import android.text.Spanned;
import android.text.style.ForegroundColorSpan;
import android.text.style.StrikethroughSpan;
import android.text.style.StyleSpan;
import android.text.style.UnderlineSpan;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Referencing the TextView
        TextView textView = (TextView) findViewById(R.id.textView);

        // The text that need to be styled using spans
        String text = "I want Red and Green to be colored and these to be Bold, Italic and Underline and Strike-through";

        // This will convert the text-string to spannable string
        // and we will used this spannableString to put spans on 
        // them and make the sub-string changes
        SpannableString spannableString = new SpannableString(text);

        // Creating the spans to style the string
        ForegroundColorSpan foregroundColorSpanRed = new ForegroundColorSpan(Color.RED);
        ForegroundColorSpan foregroundColorSpanGreen = new ForegroundColorSpan(Color.GREEN);
        StyleSpan boldSpan = new StyleSpan(Typeface.BOLD);
        StyleSpan italicSpan = new StyleSpan(Typeface.ITALIC);
        UnderlineSpan underlineSpan = new UnderlineSpan();
        StrikethroughSpan strikethroughSpan = new StrikethroughSpan();

        // Setting the spans on spannable string
        spannableString.setSpan(foregroundColorSpanRed, 7, 10, Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
        spannableString.setSpan(foregroundColorSpanGreen, 15, 20, Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
        spannableString.setSpan(boldSpan, 51, 55, Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
        spannableString.setSpan(italicSpan, 57, 63, Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
        spannableString.setSpan(underlineSpan, 68, 77, Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
        spannableString.setSpan(strikethroughSpan, 82, 96, Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);

        // Setting the spannable string on TextView
        textView.setText(spannableString);
    }
}
```

### **输出:在仿真器上运行**

![Text Styling With Spans In Android Sample Image](img/e2d431682e67304da6cb75148d8b4a37.png)
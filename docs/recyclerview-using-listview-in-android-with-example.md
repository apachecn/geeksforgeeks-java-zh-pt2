# 在安卓中使用列表视图回收视图，示例

> 原文:[https://www . geeksforgeeks . org/recycle view-using-listview-in-Android-with-example/](https://www.geeksforgeeks.org/recyclerview-using-listview-in-android-with-example/)

[recycle view](https://www.geeksforgeeks.org/android-recyclerview/)是 [ListView](https://www.geeksforgeeks.org/android-listview-in-kotlin/) 和 [GridView](https://www.geeksforgeeks.org/gridview-using-baseadapter-in-android-with-example/) 更灵活更高级的版本。RecyclerView 用于为大型数据集提供有限的窗口，这意味着它用于显示大量数据，通过维护有限数量的视图，可以非常高效地滚动这些数据。在回收视图中，我们提供数据并定义每个项目的外观，回收视图库在需要时动态创建内容。在 Android 5.0(API 级别 21.0)的材料设计中引入了 RecyclerView。

### 【RecyclerView 是如何工作的？

*   **回收视图**是一个视图组，包含与您的数据相对应的视图。它本身就是一个视图，所以它会像添加任何其他用户界面元素一样被添加到布局文件中。
*   **视图保持器对象**用于定义列表中的每个单独元素。视图持有者在创建时不包含任何内容，RecyclerView 将数据绑定到它。通过扩展**回收视图来定义视图持有者。视图支架**。
*   **适配器**用于将数据绑定到视图。通过调用适配器中的方法，RecyclerView 请求视图，并将视图绑定到它们的数据。适配器可以通过扩展**回收视图来定义。适配器**。
*   **布局管理器**排列列表中的单个元素。它包含由条目数据填充的所有视图的引用。

RecyclerView 的 LayoutManager 类提供三种内置的 layout manager

*   **Line Layout Manager:** Used to display horizontal and vertical lists.
*   **GridLayout Manager:** Used to display items in grid form.
*   **Staggered Gridlayout Manager:** Used to display items in staggered grid.

## **例**

在这个例子中，我们将使用 RecyclerView 作为列表视图。在这里，我们将使用 RecyclerView 将课程列表及其图像显示为垂直列表。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖关系**

我们将使用回收视图作为列表视图。因此，我们需要为它添加依赖项。要添加依赖项，请转到**渐变脚本>构建.渐变(模块:应用)**并添加以下依赖项。添加依赖项后，点击**立即同步**。

> 依赖项{
> 
> 实现【androidx . recycle view:recycle view:1 . 1 . 0】
> 
> }

在进一步移动之前，让我们添加一些颜色属性，以增强应用程序栏。转到 **app > res >值> colors.xml** 并添加以下颜色属性。

## XML

```java
<resources> 
    <color name="colorPrimary">#0F9D58</color> 
    <color name="colorPrimaryDark">#16E37F</color> 
    <color name="colorAccent">#03DAC5</color> 
</resources> 
```
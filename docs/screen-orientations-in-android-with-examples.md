# 安卓中的屏幕方向示例

> 原文:[https://www . geesforgeks . org/screen-orientation-in-Android-in-with-examples/](https://www.geeksforgeeks.org/screen-orientations-in-android-with-examples/)

**屏幕方位**，又称**屏幕旋转**，是安卓中活动元素的属性。当屏幕方向从一种状态变为另一种状态时，也称为**配置变化**。

**<u>屏幕方向状态</u>**
任何安卓应用程序都有各种可能的**屏幕方向状态**，例如:

*   练习信息。屏幕 _ 方向 _ 横向
*   练习信息。屏幕 _ 方向 _ 纵向
*   练习信息。屏幕 _ 方向 _ 未指定
*   练习信息。屏幕方向用户
*   练习信息。屏幕方向传感器
*   练习信息。屏幕 _ 方向 _ 后面
*   练习信息。屏幕方向传感器
*   练习信息。屏幕 _ 方向 _ 传感器 _ 风景
*   练习信息。屏幕 _ 方向 _ 传感器 _ 纵向
*   练习信息。屏幕 _ 方向 _ 反向 _ 纵向

屏幕的初始方向必须在 **[和](https://www.geeksforgeeks.org/application-manifest-file-android/)** 文件中定义。

**语法:**

## AndroidManifest.xml

```java
<activity android:name="package_name.Your_ActivityName"  
    android:screenOrientation="orientation_type">  
</activity>  
```
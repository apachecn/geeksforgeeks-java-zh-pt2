# 安卓 Firebase 实时数据库的用户认证和 CRUD 操作

> 原文:[https://www . geesforgeks . org/user-authentication-and-crud-operation-with-firebase-real-database-in-Android/](https://www.geeksforgeeks.org/user-authentication-and-crud-operation-with-firebase-realtime-database-in-android/)

[Firebase](https://www.geeksforgeeks.org/firebase-introduction/) 是谷歌的一款著名产品，被如此多的开发者用来为他们的网站和应用添加后端功能。Firebase 将使后端数据库和处理数据库的工作变得更加容易。在本文中，我们将了解一下 [Firebase 实时数据库](https://www.geeksforgeeks.org/firebase-realtime-database-with-operations-in-android-with-examples/)在安卓系统中的实现。在本文中，我们将在我们的应用程序中添加电子邮件和密码验证，同时，我们将使用 Firebase 实时数据库在我们的应用程序中执行 **CRUD(创建、读取、更新和删除)**操作。

https://www.youtube.com/watch?v=-Gvpf8tXpbc

### **本文我们将构建什么？**

在本文中，我们将构建一个简单的安卓应用程序，首先用用户的电子邮件和密码对其进行身份验证。之后，我们将在回收器视图中显示极客上可供极客使用的课程列表。我们将能够在这些课程上执行 CRUD 操作。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-655008-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210730113812/20210730_112523.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210730113812/20210730_112523.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210730113812/20210730_112523.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:将你的应用连接到 Firebase**

创建新项目后，导航到顶部栏上的“工具”选项。点击火焰基地。点击 Firebase 后，你可以看到截图中下面提到的右栏。

![](img/a7b6d13cb1e5829b641a99dc5efbd6f0.png)

在该列中，导航到 Firebase 实时数据库。点击那个选项，你会看到两个选项:连接应用程序到 Firebase 和添加 Firebase 实时数据库到你的应用程序。单击立即连接，您的应用程序将连接到 Firebase。之后点击第二个选项，现在你的应用程序连接到 Firebase。

![](img/318eefea8e1e83df3c293f058b087f34.png)

将您的应用程序连接到 Firebase 后，您将看到下面的屏幕。

![](img/170aeec3946f6e3d99ae219dd7bf023f.png)

之后，验证 Firebase 实时数据库的依赖项已经添加到我们的 Gradle 文件中。现在导航到**应用程序>渐变脚本**，并在该文件中检查是否添加了以下依赖项。如果以下依赖项没有添加到您的 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件中。在依赖项部分添加以下依赖项。下面是完整的依赖项部分，其中有身份验证和数据库的依赖项。

```java
dependencies {
    implementation 'androidx.appcompat:appcompat:1.3.0'
    implementation 'com.google.android.material:material:1.4.0'
    // dependency for picasso for loading image from url 
    implementation 'com.squareup.picasso:picasso:2.71828'
    implementation 'androidx.constraintlayout:constraintlayout:2.0.4'
    // dependency for firebase database. 
    implementation 'com.google.firebase:firebase-database:20.0.0'
    implementation platform('com.google.firebase:firebase-bom:28.2.1')
    // dependency for firebase authentication. 
    implementation 'com.google.firebase:firebase-auth'
    testImplementation 'junit:junit:4.+'
    androidTestImplementation 'androidx.test.ext:junit:1.1.3'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.4.0'
}
```

添加此依赖项后，同步您的项目，现在我们可以创建我们的应用程序了。如果你想了解更多关于连接你的应用到 Firebase。请参考这篇文章，详细了解如何将 Firebase 添加到安卓应用程序中。

**第三步:创建 4 个不同的空活动**

导航到**应用程序>您的应用程序的包名>右键单击它>新建>活动>选择空活动**并创建一个新活动。下面是我们在创建新活动时必须通过的四个不同活动的名称。

*   **添加课程活动**:这个活动我们将用于添加新的课程。
*   **编辑课程活动**:本活动将用于编辑我们的课程以及删除我们的课程。
*   **登录活动**:该活动将用于现有用户登录的登录目的。
*   **注册活动**:该活动用于注册新用户。

**MainActivity.java**文件已经存在，我们将在[循环查看](https://www.geeksforgeeks.org/android-recyclerview/)中显示课程列表。

**第 4 步:使用 AndroidManifest.xml 文件**

导航至**应用程序> AndroidManifest.xml** 文件，并为其添加互联网权限。下面是 AndroidManifest.xml 文件的完整代码。在这个文件中，我们还将启动器活动更改为登录活动。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.gtappdevelopers.firebasecrudapp">

    <!--permissions for internet-->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.FirebaseCrudApp">
        <activity
            android:name=".EditCourseActivity"
            android:label="Edit Course" />
        <activity
            android:name=".AddCourseActivity"
            android:label="Add Course" />
        <activity
            android:name=".RegisterActivity"
            android:label="Register" />
        <!--login activity is set as launcher activity-->
        <activity android:name=".LoginActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".MainActivity" />
    </application>

</manifest>
```

**第五步:更新 colors.xml 文件**

导航至**应用程序>RES>values>colors . XML**并添加以下颜色。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<resources xmlns:tools="http://schemas.android.com/tools">
    <color name="purple_200">#296D98</color>
    <color name="purple_500">#296D98</color>
    <color name="purple_700">#296D98</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>

    <color name="black_shade_1">#0e2433</color>
    <color name="black_shade_2">#1C4966</color>

    <color name="black_shade_3">#22252D</color>
    <color name="mtrl_textinput_default_box_stroke_color" tools:override="true">#296D98</color>

    <color name="light_blue_shade_1">#296D98</color>
    <color name="gray">#424242</color>
    <color name="yellow">#ffa500</color>
    <color name="dark_blue_shade">#0D2162</color>
    <color name="dark_blue_shade_2">#17388E</color>
    <color name="light_blue_shade">#12B2E6</color>

</resources>
```

**第 6 步:更新我们的主题. xml 文件**

导航至**应用程序>RES>values>themes . XML**并添加以下代码。

## 可扩展标记语言

```java
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.FirebaseCrudApp" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>

    <style name="AppBottomSheetDialogTheme" parent="Theme.Design.Light.BottomSheetDialog">
        <item name="bottomSheetStyle">@style/AppModalStyle</item>
    </style>

    <style name="BottomSheetDialogTheme" parent="Theme.Design.Light.BottomSheetDialog">
        <item name="bottomSheetStyle">@style/BottomSheetStyle</item>
    </style>

    <style name="BottomSheetStyle" parent="Widget.Design.BottomSheet.Modal">
        <item name="android:background">@android:color/transparent</item>
    </style>

    <style name="AppModalStyle" parent="Widget.Design.BottomSheet.Modal">
        <item name="android:background">@drawable/rounded_drawable</item>
    </style>

    <style name="LoginTextInputLayoutStyle" parent="Widget.MaterialComponents.TextInputLayout.OutlinedBox.Dense">
        <item name="boxStrokeColor">#296D98</item>
        <item name="boxStrokeWidth">1dp</item>
    </style>

</resources>
```

**第 7 步:为我们的按钮和自定义进度条背景**创建自定义背景

导航到**应用程序> res >可绘制>右键单击它>新建可绘制资源文件**并将其命名为**按钮 _ 后退**并向其添加以下代码。代码中添加了注释，以便详细了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <!--for specifying corner radius-->
    <corners android:radius="20dp" />
    <!-- for specifying solid color-->
    <solid android:color="@color/black_shade_1" />

</shape>
```

导航到**应用程序> res >可绘制>右键单击它>新建可绘制资源文件**并将其命名为 **progress_back** 并添加以下代码。代码中添加了注释，以便详细了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<rotate 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:toDegrees="360">

    <!--shape tag is used to
        build a shape in XML-->
    <shape
        android:innerRadiusRatio="3"
        android:shape="ring"
        android:thicknessRatio="8"
        android:useLevel="false">

        <!--set the size of the shape-->
        <size
            android:width="76dip"
            android:height="76dip" />

        <!--set the color gradients
            of the shape-->
        <gradient
            android:angle="0"
            android:endColor="#00ffffff"
            android:startColor="@color/purple_200"
            android:type="sweep"
            android:useLevel="false" />
    </shape>

</rotate>
```

**第 8 步:使用 activity_register.xml 文件**

导航至**应用程序>RES>activity _ register . XML**，并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/black_shade_1"
    tools:context=".RegisterActivity">

    <!--edit text for user name-->
    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/idTILUserName"
        style="@style/LoginTextInputLayoutStyle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="20dp"
        android:layout_marginTop="140dp"
        android:layout_marginEnd="20dp"
        android:hint="Enter User Name"
        android:padding="5dp"
        android:textColorHint="@color/white"
        app:hintTextColor="@color/white">

        <com.google.android.material.textfield.TextInputEditText
            android:id="@+id/idEdtUserName"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:ems="10"
            android:importantForAutofill="no"
            android:inputType="textEmailAddress"
            android:textColor="@color/white"
            android:textColorHint="@color/white"
            android:textSize="14sp" />
    </com.google.android.material.textfield.TextInputLayout>

    <!--edit text for user password-->
    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/idTILPassword"
        style="@style/LoginTextInputLayoutStyle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTILUserName"
        android:layout_marginStart="20dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="20dp"
        android:hint="Enter Your Password"
        android:padding="5dp"
        android:textColorHint="@color/white"
        app:hintTextColor="@color/white">

        <com.google.android.material.textfield.TextInputEditText
            android:id="@+id/idEdtPassword"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:ems="10"
            android:importantForAutofill="no"
            android:inputType="textPassword"
            android:textColor="@color/white"
            android:textColorHint="@color/white"
            android:textSize="14sp" />
    </com.google.android.material.textfield.TextInputLayout>

    <!--edit text for confirmation of user password-->

    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/idTILConfirmPassword"
        style="@style/LoginTextInputLayoutStyle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTILPassword"
        android:layout_marginStart="20dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="20dp"
        android:hint="Confirm Your Password"
        android:padding="5dp"
        android:textColorHint="@color/white"
        app:hintTextColor="@color/white">

        <com.google.android.material.textfield.TextInputEditText
            android:id="@+id/idEdtConfirmPassword"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:ems="10"
            android:importantForAutofill="no"
            android:inputType="textPassword"
            android:textColor="@color/white"
            android:textColorHint="@color/white"
            android:textSize="14sp" />
    </com.google.android.material.textfield.TextInputLayout>

    <!--button for creating user account.-->
    <Button
        android:id="@+id/idBtnRegister"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTILConfirmPassword"
        android:layout_marginStart="25dp"
        android:layout_marginTop="40dp"
        android:layout_marginEnd="25dp"
        android:background="@drawable/button_back"
        android:text="Register"
        android:textAllCaps="false" />

    <!--text view for displaying a text on 
        clicking we will open a login page-->
    <TextView
        android:id="@+id/idTVLoginUser"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idBtnRegister"
        android:layout_marginTop="40dp"
        android:gravity="center"
        android:padding="10dp"
        android:text="Already a User ? Login Here"
        android:textAlignment="center"
        android:textAllCaps="false"
        android:textColor="@color/white"
        android:textSize="18sp" />

    <!--progress bar as a loading indicator-->
    <ProgressBar
        android:id="@+id/idPBLoading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:indeterminate="true"
        android:indeterminateDrawable="@drawable/progress_back"
        android:visibility="gone" />

</RelativeLayout>
```

**第九步:使用 RegisterActivity.java 文件**

导航到**应用程序> java >你的应用程序的包名>RegisterActivity.java**文件，并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.firebasecrudapp;

import android.content.Intent;
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.ProgressBar;
import android.widget.TextView;
import android.widget.Toast;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.android.material.textfield.TextInputEditText;
import com.google.firebase.auth.AuthResult;
import com.google.firebase.auth.FirebaseAuth;

public class RegisterActivity extends AppCompatActivity {

    // cretaing variables for edit text and textview, 
    // firebase auth, button and progress bar. 
    private TextInputEditText userNameEdt, passwordEdt, confirmPwdEdt;
    private TextView loginTV;
    private Button registerBtn;
    private FirebaseAuth mAuth;
    private ProgressBar loadingPB;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_register);

        // initializing all our variables. 
        userNameEdt = findViewById(R.id.idEdtUserName);
        passwordEdt = findViewById(R.id.idEdtPassword);
        loadingPB = findViewById(R.id.idPBLoading);
        confirmPwdEdt = findViewById(R.id.idEdtConfirmPassword);
        loginTV = findViewById(R.id.idTVLoginUser);
        registerBtn = findViewById(R.id.idBtnRegister);
        mAuth = FirebaseAuth.getInstance();

        // adding on click for login tv.
        loginTV.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // opening a login activity on clicking login text. 
                Intent i = new Intent(RegisterActivity.this, LoginActivity.class);
                startActivity(i);
            }
        });

        // adding click listener for register button.
        registerBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // hiding our progress bar. 
                loadingPB.setVisibility(View.VISIBLE);

                // getting data fro =m our edit text. 
                String userName = userNameEdt.getText().toString();
                String pwd = passwordEdt.getText().toString();
                String cnfPwd = confirmPwdEdt.getText().toString();

                // checking if the password and confirm password is equal or not. 
                if (!pwd.equals(cnfPwd)) {
                    Toast.makeText(RegisterActivity.this, "Please check both having same password..", Toast.LENGTH_SHORT).show();
                } else if (TextUtils.isEmpty(userName) && TextUtils.isEmpty(pwd) && TextUtils.isEmpty(cnfPwd)) {

                    // checking if the text fields are empty or not. 
                    Toast.makeText(RegisterActivity.this, "Please enter your credentials..", Toast.LENGTH_SHORT).show();
                } else {

                    // on below line we are creating a new user by passing email and password.
                    mAuth.createUserWithEmailAndPassword(userName, pwd).addOnCompleteListener(new OnCompleteListener<AuthResult>() {
                        @Override
                        public void onComplete(@NonNull Task<AuthResult> task) {
                            // on below line we are checking if the task is success or not. 
                            if (task.isSuccessful()) {

                                // in on success method we are hiding our progress bar and opening a login activity. 
                                loadingPB.setVisibility(View.GONE);
                                Toast.makeText(RegisterActivity.this, "User Registered..", Toast.LENGTH_SHORT).show();
                                Intent i = new Intent(RegisterActivity.this, LoginActivity.class);
                                startActivity(i);
                                finish();
                            } else {

                                // in else condition we are displaying a failure toast message. 
                                loadingPB.setVisibility(View.GONE);
                                Toast.makeText(RegisterActivity.this, "Fail to register user..", Toast.LENGTH_SHORT).show();
                            }
                        }
                    });
                }
            }
        });
    }
}
```

**第十步:使用 activity_login.xml 文件**

导航至**应用程序>RES>activity _ log in . XML**，并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/black_shade_1"
    tools:context=".LoginActivity">

    <!--edit text for user name-->
    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/idTILUserName"
        style="@style/LoginTextInputLayoutStyle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="20dp"
        android:layout_marginTop="140dp"
        android:layout_marginEnd="20dp"
        android:hint="Enter User Name"
        android:padding="5dp"
        android:textColorHint="@color/white"
        app:hintTextColor="@color/white">

        <com.google.android.material.textfield.TextInputEditText
            android:id="@+id/idEdtUserName"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:ems="10"
            android:importantForAutofill="no"
            android:inputType="textEmailAddress"
            android:textColor="@color/white"
            android:textColorHint="@color/white"
            android:textSize="14sp" />
    </com.google.android.material.textfield.TextInputLayout>

    <!--edit text for password-->
    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/idTILPassword"
        style="@style/LoginTextInputLayoutStyle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTILUserName"
        android:layout_marginStart="20dp"
        android:layout_marginTop="40dp"
        android:layout_marginEnd="20dp"
        android:hint="Enter your Password"
        android:padding="5dp"
        android:textColorHint="@color/white"
        app:hintTextColor="@color/white">

        <com.google.android.material.textfield.TextInputEditText
            android:id="@+id/idEdtPassword"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:ems="10"
            android:importantForAutofill="no"
            android:inputType="textPassword"
            android:textColor="@color/white"
            android:textColorHint="@color/white"
            android:textSize="14sp" />
    </com.google.android.material.textfield.TextInputLayout>

    <!--button for login-->
    <Button
        android:id="@+id/idBtnLogin"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTILPassword"
        android:layout_marginStart="25dp"
        android:layout_marginTop="40dp"
        android:layout_marginEnd="25dp"
        android:background="@drawable/button_back"
        android:text="Login"
        android:textAllCaps="false"
        />

    <!--text view for creating a new account-->
    <TextView
        android:id="@+id/idTVNewUser"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idBtnLogin"
        android:layout_marginTop="40dp"
        android:gravity="center"
        android:padding="10dp"
        android:text="New User ? Register Here"
        android:textAlignment="center"
        android:textAllCaps="false"
        android:textColor="@color/white"
        android:textSize="18sp" />

    <!--progress-bar for loading indicator-->
    <ProgressBar
        android:id="@+id/idPBLoading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVNewUser"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="10dp"
        android:indeterminate="true"
        android:indeterminateDrawable="@drawable/progress_back"
        android:visibility="gone" />

</RelativeLayout>
```

**第 11 步:使用 LoginActivity.java 文件**

导航到**应用程序> java >你的应用程序的包名>LoginActivity.java 文件**并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.firebasecrudapp;

import android.content.Intent;
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.ProgressBar;
import android.widget.TextView;
import android.widget.Toast;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.android.material.textfield.TextInputEditText;
import com.google.firebase.auth.AuthResult;
import com.google.firebase.auth.FirebaseAuth;
import com.google.firebase.auth.FirebaseUser;

public class LoginActivity extends AppCompatActivity {

    // creating variable for edit text, textview, 
    // button, progress bar and firebase auth.
    private TextInputEditText userNameEdt, passwordEdt;
    private Button loginBtn;
    private TextView newUserTV;
    private FirebaseAuth mAuth;
    private ProgressBar loadingPB;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_login);
        // initializing all our variables. 
        userNameEdt = findViewById(R.id.idEdtUserName);
        passwordEdt = findViewById(R.id.idEdtPassword);
        loginBtn = findViewById(R.id.idBtnLogin);
        newUserTV = findViewById(R.id.idTVNewUser);
        mAuth = FirebaseAuth.getInstance();
        loadingPB = findViewById(R.id.idPBLoading);
        // adding click listener for our new user tv.
        newUserTV.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on below line opening a login activity. 
                Intent i = new Intent(LoginActivity.this, RegisterActivity.class);
                startActivity(i);
            }
        });

        // adding on click listener for our login button. 
        loginBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // hiding our progress bar. 
                loadingPB.setVisibility(View.VISIBLE);
                // getting data from our edit text on below line. 
                String email = userNameEdt.getText().toString();
                String password = passwordEdt.getText().toString();
                // on below line validating the text input. 
                if (TextUtils.isEmpty(email) && TextUtils.isEmpty(password)) {
                    Toast.makeText(LoginActivity.this, "Please enter your credentials..", Toast.LENGTH_SHORT).show();
                    return;
                }
                // on below line we are calling a sign in method and passing email and password to it. 
                mAuth.signInWithEmailAndPassword(email, password).addOnCompleteListener(new OnCompleteListener<AuthResult>() {
                    @Override
                    public void onComplete(@NonNull Task<AuthResult> task) {
                        // on below line we are checking if the task is succes or not. 
                        if (task.isSuccessful()) {
                            // on below line we are hiding our progress bar. 
                            loadingPB.setVisibility(View.GONE);
                            Toast.makeText(LoginActivity.this, "Login Successful..", Toast.LENGTH_SHORT).show();
                            // on below line we are opening our mainactivity. 
                            Intent i = new Intent(LoginActivity.this, MainActivity.class);
                            startActivity(i);
                            finish();
                        } else {
                            // hiding our progress bar and displaying a toast message.
                            loadingPB.setVisibility(View.GONE);
                            Toast.makeText(LoginActivity.this, "Please enter valid user credentials..", Toast.LENGTH_SHORT).show();
                        }
                    }
                });
            }
        });
    }

    @Override
    protected void onStart() {
        super.onStart();
        // in on start method checking if
        // the user is already sign in. 
        FirebaseUser user = mAuth.getCurrentUser();
        if (user != null) {
            // if the user is not null then we are
              // opening a main activity on below line. 
            Intent i = new Intent(LoginActivity.this, MainActivity.class);
            startActivity(i);
            this.finish();
        }
    }
}
```

**第 12 步:为我们的数据创建一个模态类，显示在我们的回收视图**中

导航到**应用程序> java >你的应用程序的包名>右键点击它>新建> Java 类**并将其命名为 **CourseRVModal** 并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.firebasecrudapp;

import android.os.Parcel;
import android.os.Parcelable;

public class CourseRVModal implements Parcelable {
    // creating variables for our different fields. 
    private String courseName;
    private String courseDescription;
    private String coursePrice;
    private String bestSuitedFor;
    private String courseImg;
    private String courseLink;
    private String courseId;

    public String getCourseId() {
        return courseId;
    }

    public void setCourseId(String courseId) {
        this.courseId = courseId;
    }

    // creating an empty constructor. 
    public CourseRVModal() {

    }

    protected CourseRVModal(Parcel in) {
        courseName = in.readString();
        courseId = in.readString();
        courseDescription = in.readString();
        coursePrice = in.readString();
        bestSuitedFor = in.readString();
        courseImg = in.readString();
        courseLink = in.readString();
    }

    public static final Creator<CourseRVModal> CREATOR = new Creator<CourseRVModal>() {
        @Override
        public CourseRVModal createFromParcel(Parcel in) {
            return new CourseRVModal(in);
        }

        @Override
        public CourseRVModal[] newArray(int size) {
            return new CourseRVModal[size];
        }
    };

    // creating getter and setter methods. 
    public String getCourseName() {
        return courseName;
    }

    public void setCourseName(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseDescription() {
        return courseDescription;
    }

    public void setCourseDescription(String courseDescription) {
        this.courseDescription = courseDescription;
    }

    public String getCoursePrice() {
        return coursePrice;
    }

    public void setCoursePrice(String coursePrice) {
        this.coursePrice = coursePrice;
    }

    public String getBestSuitedFor() {
        return bestSuitedFor;
    }

    public void setBestSuitedFor(String bestSuitedFor) {
        this.bestSuitedFor = bestSuitedFor;
    }

    public String getCourseImg() {
        return courseImg;
    }

    public void setCourseImg(String courseImg) {
        this.courseImg = courseImg;
    }

    public String getCourseLink() {
        return courseLink;
    }

    public void setCourseLink(String courseLink) {
        this.courseLink = courseLink;
    }

    public CourseRVModal(String courseId, String courseName, String courseDescription, String coursePrice, String bestSuitedFor, String courseImg, String courseLink) {
        this.courseName = courseName;
        this.courseId = courseId;
        this.courseDescription = courseDescription;
        this.coursePrice = coursePrice;
        this.bestSuitedFor = bestSuitedFor;
        this.courseImg = courseImg;
        this.courseLink = courseLink;
    }

    @Override
    public int describeContents() {
        return 0;
    }

    @Override
    public void writeToParcel(Parcel dest, int flags) {
        dest.writeString(courseName);
        dest.writeString(courseId);
        dest.writeString(courseDescription);
        dest.writeString(coursePrice);
        dest.writeString(bestSuitedFor);
        dest.writeString(courseImg);
        dest.writeString(courseLink);
    }
}
```

### **在数据库中创建操作**

**第 13 步:使用 activity_add_course.xml 文件**

导航至**应用程序> res >布局> activity_add_course.xml** 并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<ScrollView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/black_shade_1"
    tools:context=".AddCourseActivity">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <!--edit text for course name-->
            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/idTILCourseName"
                style="@style/LoginTextInputLayoutStyle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginRight="10dp"
                android:hint="Enter Course Name"
                android:padding="5dp"
                android:textColorHint="@color/white"
                app:hintTextColor="@color/white">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/idEdtCourseName"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:ems="10"
                    android:importantForAutofill="no"
                    android:inputType="textImeMultiLine|textMultiLine"
                    android:textColor="@color/white"
                    android:textColorHint="@color/white"
                    android:textSize="14sp" />
            </com.google.android.material.textfield.TextInputLayout>

            <!--edit text for course price-->
            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/idTILCoursePrice"
                style="@style/LoginTextInputLayoutStyle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginRight="10dp"
                android:hint="Enter Course Price"
                android:padding="5dp"
                android:textColorHint="@color/white"
                app:boxStrokeColor="@color/purple_200"
                app:hintTextColor="@color/white">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/idEdtCoursePrice"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:ems="10"
                    android:importantForAutofill="no"
                    android:inputType="phone"
                    android:textColor="@color/white"
                    android:textColorHint="@color/white"
                    android:textSize="14sp"
                    app:boxStrokeColor="@color/purple_200" />
            </com.google.android.material.textfield.TextInputLayout>

            <!--edit text for course suited for-->
            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/idTILCourseSuitedFor"
                style="@style/LoginTextInputLayoutStyle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginRight="10dp"
                android:hint="Enter Course Suited For"
                android:padding="5dp"
                android:textColorHint="@color/white"
                app:hintTextColor="@color/white">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/idEdtSuitedFor"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:ems="10"
                    android:importantForAutofill="no"
                    android:inputType="textImeMultiLine|textMultiLine"
                    android:textColor="@color/white"
                    android:textColorHint="@color/white"
                    android:textSize="14sp" />
            </com.google.android.material.textfield.TextInputLayout>

            <!--edit text for course image link-->
            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/idTILCourseImageLink"
                style="@style/LoginTextInputLayoutStyle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginRight="10dp"
                android:hint="Enter Course Image Link"
                android:padding="5dp"
                android:textColorHint="@color/white"
                app:hintTextColor="@color/white">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/idEdtCourseImageLink"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:ems="10"
                    android:importantForAutofill="no"
                    android:inputType="textImeMultiLine|textMultiLine"
                    android:textColor="@color/white"
                    android:textColorHint="@color/white"
                    android:textSize="14sp" />
            </com.google.android.material.textfield.TextInputLayout>

            <!--edit text for course link-->
            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/idTILCourseLink"
                style="@style/LoginTextInputLayoutStyle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginRight="10dp"
                android:hint="Enter Course Link"
                android:padding="5dp"
                android:textColorHint="@color/white"
                app:hintTextColor="@color/white">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/idEdtCourseLink"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:ems="10"
                    android:importantForAutofill="no"
                    android:inputType="textImeMultiLine|textMultiLine"
                    android:textColor="@color/white"
                    android:textColorHint="@color/white"
                    android:textSize="14sp" />
            </com.google.android.material.textfield.TextInputLayout>

            <!--edit text for course description-->
            <com.google.android.material.textfield.TextInputLayout
                android:id="@+id/idTILCourseDescription"
                style="@style/LoginTextInputLayoutStyle"
                android:layout_width="match_parent"
                android:layout_height="200dp"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginRight="10dp"
                android:hint="Enter Course Description"
                android:padding="5dp"
                android:textColorHint="@color/white"
                app:hintTextColor="@color/white">

                <com.google.android.material.textfield.TextInputEditText
                    android:id="@+id/idEdtCourseDescription"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:ems="10"
                    android:importantForAutofill="no"
                    android:inputType="textImeMultiLine|textMultiLine"
                    android:textColor="@color/white"
                    android:textColorHint="@color/white"
                    android:textSize="14sp" />
            </com.google.android.material.textfield.TextInputLayout>

            <!--button for adding a new course-->
            <Button
                android:id="@+id/idBtnAddCourse"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginStart="10dp"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="10dp"
                android:layout_marginBottom="10dp"
                android:background="@drawable/button_back"
                android:text="Add Your Course"
                android:textAllCaps="false" />

        </LinearLayout>

        <!--progress bar for loading indicator-->
        <ProgressBar
            android:id="@+id/idPBLoading"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerInParent="true"
            android:layout_gravity="center"
            android:indeterminate="true"
            android:indeterminateDrawable="@drawable/progress_back"
            android:visibility="gone" />

    </RelativeLayout>
</ScrollView>
```

**步骤 14:使用 AddCourseActivity.java 文件**

导航到**应用程序> java >你的应用程序的包名>AddCourseActivity.java**文件，并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.firebasecrudapp;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ProgressBar;
import android.widget.Toast;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import com.google.android.material.textfield.TextInputEditText;
import com.google.firebase.database.DataSnapshot;
import com.google.firebase.database.DatabaseError;
import com.google.firebase.database.DatabaseReference;
import com.google.firebase.database.FirebaseDatabase;
import com.google.firebase.database.ValueEventListener;

public class AddCourseActivity extends AppCompatActivity {

    // creating variables for our button, edit text,
    // firebase database, database reference, progress bar.
    private Button addCourseBtn;
    private TextInputEditText courseNameEdt, courseDescEdt, coursePriceEdt, bestSuitedEdt, courseImgEdt, courseLinkEdt;
    FirebaseDatabase firebaseDatabase;
    DatabaseReference databaseReference;
    private ProgressBar loadingPB;
    private String courseID;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_add_course);
        // initializing all our variables. 
        addCourseBtn = findViewById(R.id.idBtnAddCourse);
        courseNameEdt = findViewById(R.id.idEdtCourseName);
        courseDescEdt = findViewById(R.id.idEdtCourseDescription);
        coursePriceEdt = findViewById(R.id.idEdtCoursePrice);
        bestSuitedEdt = findViewById(R.id.idEdtSuitedFor);
        courseImgEdt = findViewById(R.id.idEdtCourseImageLink);
        courseLinkEdt = findViewById(R.id.idEdtCourseLink);
        loadingPB = findViewById(R.id.idPBLoading);
        firebaseDatabase = FirebaseDatabase.getInstance();
        // on below line creating our database reference. 
        databaseReference = firebaseDatabase.getReference("Courses");
        // adding click listener for our add course button. 
        addCourseBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                loadingPB.setVisibility(View.VISIBLE);
                // getting data from our edit text. 
                String courseName = courseNameEdt.getText().toString();
                String courseDesc = courseDescEdt.getText().toString();
                String coursePrice = coursePriceEdt.getText().toString();
                String bestSuited = bestSuitedEdt.getText().toString();
                String courseImg = courseImgEdt.getText().toString();
                String courseLink = courseLinkEdt.getText().toString();
                courseID = courseName;
                // on below line we are passing all data to our modal class. 
                CourseRVModal courseRVModal = new CourseRVModal(courseID, courseName, courseDesc, coursePrice, bestSuited, courseImg, courseLink);
                // on below line we are calling a add value event 
                // to pass data to firebase database. 
                databaseReference.addValueEventListener(new ValueEventListener() {
                    @Override
                    public void onDataChange(@NonNull DataSnapshot snapshot) {
                        // on below line we are setting data in our firebase database. 
                        databaseReference.child(courseID).setValue(courseRVModal);
                        // displaying a toast message. 
                        Toast.makeText(AddCourseActivity.this, "Course Added..", Toast.LENGTH_SHORT).show();
                        // starting a main activity. 
                        startActivity(new Intent(AddCourseActivity.this, MainActivity.class));
                    }

                    @Override
                    public void onCancelled(@NonNull DatabaseError error) {
                        // displaying a failure message on below line. 
                        Toast.makeText(AddCourseActivity.this, "Fail to add Course..", Toast.LENGTH_SHORT).show();
                    }
                });
            }
        });
    }
}
```

### **从数据库读取操作**

**第 15 步:在我们的回收视图中为每个课程创建一个项目。**

导航至 **app > res >右键单击>新建布局资源文件**并将其命名为 **course_rv_item** 并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_gravity="center"
    android:layout_margin="5dp"
    app:cardCornerRadius="4dp"
    app:cardElevation="3dp">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/black_shade_1">

        <!--image view for our course-->
        <ImageView
            android:id="@+id/idIVCourse"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:scaleType="centerCrop" />

        <!--text view for course name-->
        <TextView
            android:id="@+id/idTVCOurseName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idIVCourse"
            android:layout_margin="3dp"
            android:layout_toStartOf="@id/idTVCousePrice"
            android:layout_toLeftOf="@id/idTVCousePrice"
            android:padding="4dp"
            android:text="Course Name"
            android:textColor="@color/white"
            android:textSize="15sp"
            android:textStyle="bold" />

        <!--text view for course price-->
        <TextView
            android:id="@+id/idTVCousePrice"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/idIVCourse"
            android:layout_alignParentEnd="true"
            android:layout_alignParentRight="true"
            android:layout_margin="3dp"
            android:gravity="center"
            android:padding="4dp"
            android:text="Price"
            android:textColor="@color/white"
            android:textSize="15sp"
            android:textStyle="bold" />

    </RelativeLayout>

</androidx.cardview.widget.CardView>
```
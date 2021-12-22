# 安卓中的音池示例

> 原文:[https://www . geesforgeks . org/sound pool-in-Android-in-with-examples/](https://www.geeksforgeeks.org/soundpool-in-android-with-examples/)

在本文中，我们将学习如何在安卓中添加 [**【音池】**](https://developer.android.com/reference/android/media/SoundPool) 类。音频样本的集合可以从资源加载到内存中，并且可以使用。 **SoundPool** 类用于播放短的重复声音，而 MediaPlayer 类用于播放较长的片段，如音乐。它使用**媒体播放器**服务来解码音频。外汇:-一个游戏包括几个级别的游戏。对于每个级别，都有一组仅由该级别使用的独特声音。为此，我们使用了 **SoundPool** 类来做我们的工作。因此，学习 SoundPool 课程可以更好地理解如何处理短音频剪辑。

**进场:**

1.  创建一个新的**安卓资源目录**，为此
    右键单击资源文件夹- >安卓资源目录，
    确保选择资源类型为原始。在这个原始文件夹中粘贴您的音频剪辑。
2.  在 **activity_main.xml** 文件中添加以下代码。这里添加了三个按钮。每个按钮如果被点击将调用**播放声音**方法。

    ## activity _ main . XML

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="center"
        tools:context=".MainActivity">

        <Button
            android:id="@+id/button_sound1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:onClick="playSound"
            android:text="Game Over"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent" />

        <Button
            android:id="@+id/button_sound2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:onClick="playSound"
            android:text="Player Died"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            app:layout_constraintVertical_bias="0.472" />

        <Button
            android:id="@+id/button_sound3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:onClick="playSound"
            android:text="Level Complete"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            app:layout_constraintVertical_bias="0.472" />

    </androidx.constraintlayout.widget.ConstraintLayout>
    ```

3.  Add the following code in **MainActivity.java** file. Here, an object of SoundPool class is created and three audio clips, **game_over**, **level_complete** and **player_died** are added using **load** method. playSound method is also added which plays the audio clip associated with the respective button.

    ## MainActivity.java

    ```
    package org.geeksforgeeks.gfgsoundpool;

    import androidx.appcompat.app.AppCompatActivity;
    import android.media.AudioAttributes;
    import android.media.AudioManager;
    import android.media.SoundPool;
    import android.os.Build;
    import android.os.Bundle;
    import android.view.View;

    public class MainActivity
        extends AppCompatActivity {
        SoundPool soundPool;
        int game_over,
            level_complete,
            player_died;

        @Override
        protected void onCreate(
            Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            if (Build.VERSION.SDK_INT
                >= Build.VERSION_CODES.LOLLIPOP) {
                AudioAttributes
                    audioAttributes
                    = new AudioAttributes
                          .Builder()
                          .setUsage(
                              AudioAttributes
                                  .USAGE_ASSISTANCE_SONIFICATION)
                          .setContentType(
                              AudioAttributes
                                  .CONTENT_TYPE_SONIFICATION)
                          .build();
                soundPool
                    = new SoundPool
                          .Builder()
                          .setMaxStreams(3)
                          .setAudioAttributes(
                              audioAttributes)
                          .build();
            }
            else {
                soundPool
                    = new SoundPool(
                        3,
                        AudioManager.STREAM_MUSIC,
                        0);
            }

            // This load function takes
            // three parameter context,
            // file_name and priority.
            game_over
                = soundPool
                      .load(
                          this,
                          R.raw.game_over,
                          1);
            level_complete
                = soundPool.load(
                    this,
                    R.raw.level_complete,
                    1);
            player_died
                = soundPool.load(
                    this,
                    R.raw.player_died,
                    1);
        }

        public void playSound(View v)
        {
            switch (v.getId()) {

            case R.id.button_sound1:

                // This play function
                // takes five parameter
                // leftVolume, rightVolume,
                // priority, loop and rate.
                soundPool.play(
                    game_over, 1, 1, 0, 0, 1);
                soundPool.autoPause();
                break;

            case R.id.button_sound2:
                soundPool.play(
                    player_died, 1, 1, 0, 0, 1);
                break;

            case R.id.button_sound3:
                soundPool.play(
                    level_complete, 1, 1, 0, 0, 1);
                break;
            }
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-443190-1" width="320" height="350" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200630220913/20200630-220134-720x1600.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200630220913/20200630-220134-720x1600.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200630220913/20200630-220134-720x1600.mp4)</video>
# 如何使用 Java 播放音频文件

> 原文:[https://www.geeksforgeeks.org/play-audio-file-using-java/](https://www.geeksforgeeks.org/play-audio-file-using-java/)

在本文中，我们将看到，我们如何用纯 java 播放音频文件，这里的纯意思是，我们不打算使用任何外部库。借助这篇文章，你可以创建自己的音乐播放器。Java 内置库只支持 AIFC、AIFF、AU、SND 和 WAVE 格式。
有 2 个不同的接口可用于此目的 Clip 和 SourceDataLine。在本文中，我们将讨论仅使用剪辑播放音频文件，并查看剪辑的各种方法。我们将涵盖以下操作:

1.  开始吧。
2.  暂停一下。
3.  简历。
4.  重启。
5.  停止
6.  跳到播放的特定位置。

**使用剪辑播放音频**

Clip 是一个 java 接口，在 javax.sound.sampled 包中提供，并在 Java7 中引入。
**播放剪辑对象需要遵循以下步骤。**

1.  使用音频系统创建音频输入流的对象。音频输入流将音频文件转换为流。
2.  从音频系统获取剪辑参考对象。
3.  通过使用剪辑界面的 open()方法将音频数据读入剪辑的音频输入流。
4.  为剪辑设置所需的属性，如帧位置、循环、微秒位置。
5.  开始剪辑

```java
// Java program to play an Audio
// file using Clip Object
import java.io.File;
import java.io.IOException;
import java.util.Scanner;

import javax.sound.sampled.AudioInputStream;
import javax.sound.sampled.AudioSystem;
import javax.sound.sampled.Clip;
import javax.sound.sampled.LineUnavailableException;
import javax.sound.sampled.UnsupportedAudioFileException;

public class SimpleAudioPlayer 
{

    // to store current position
    Long currentFrame;
    Clip clip;

    // current status of clip
    String status;

    AudioInputStream audioInputStream;
    static String filePath;

    // constructor to initialize streams and clip
    public SimpleAudioPlayer()
        throws UnsupportedAudioFileException,
        IOException, LineUnavailableException 
    {
        // create AudioInputStream object
        audioInputStream = 
                AudioSystem.getAudioInputStream(new File(filePath).getAbsoluteFile());

        // create clip reference
        clip = AudioSystem.getClip();

        // open audioInputStream to the clip
        clip.open(audioInputStream);

        clip.loop(Clip.LOOP_CONTINUOUSLY);
    }

    public static void main(String[] args) 
    {
        try
        {
            filePath = "Your path for the file";
            SimpleAudioPlayer audioPlayer = 
                            new SimpleAudioPlayer();

            audioPlayer.play();
            Scanner sc = new Scanner(System.in);

            while (true)
            {
                System.out.println("1\. pause");
                System.out.println("2\. resume");
                System.out.println("3\. restart");
                System.out.println("4\. stop");
                System.out.println("5\. Jump to specific time");
                int c = sc.nextInt();
                audioPlayer.gotoChoice(c);
                if (c == 4)
                break;
            }
            sc.close();
        } 

        catch (Exception ex) 
        {
            System.out.println("Error with playing sound.");
            ex.printStackTrace();

          }
    }

    // Work as the user enters his choice

    private void gotoChoice(int c)
            throws IOException, LineUnavailableException, UnsupportedAudioFileException 
    {
        switch (c) 
        {
            case 1:
                pause();
                break;
            case 2:
                resumeAudio();
                break;
            case 3:
                restart();
                break;
            case 4:
                stop();
                break;
            case 5:
                System.out.println("Enter time (" + 0 + 
                ", " + clip.getMicrosecondLength() + ")");
                Scanner sc = new Scanner(System.in);
                long c1 = sc.nextLong();
                jump(c1);
                break;

        }

    }

    // Method to play the audio
    public void play() 
    {
        //start the clip
        clip.start();

        status = "play";
    }

    // Method to pause the audio
    public void pause() 
    {
        if (status.equals("paused")) 
        {
            System.out.println("audio is already paused");
            return;
        }
        this.currentFrame = 
        this.clip.getMicrosecondPosition();
        clip.stop();
        status = "paused";
    }

    // Method to resume the audio
    public void resumeAudio() throws UnsupportedAudioFileException,
                                IOException, LineUnavailableException 
    {
        if (status.equals("play")) 
        {
            System.out.println("Audio is already "+
            "being played");
            return;
        }
        clip.close();
        resetAudioStream();
        clip.setMicrosecondPosition(currentFrame);
        this.play();
    }

    // Method to restart the audio
    public void restart() throws IOException, LineUnavailableException,
                                            UnsupportedAudioFileException 
    {
        clip.stop();
        clip.close();
        resetAudioStream();
        currentFrame = 0L;
        clip.setMicrosecondPosition(0);
        this.play();
    }

    // Method to stop the audio
    public void stop() throws UnsupportedAudioFileException,
    IOException, LineUnavailableException 
    {
        currentFrame = 0L;
        clip.stop();
        clip.close();
    }

    // Method to jump over a specific part
    public void jump(long c) throws UnsupportedAudioFileException, IOException,
                                                        LineUnavailableException 
    {
        if (c > 0 && c < clip.getMicrosecondLength()) 
        {
            clip.stop();
            clip.close();
            resetAudioStream();
            currentFrame = c;
            clip.setMicrosecondPosition(c);
            this.play();
        }
    }

    // Method to reset audio stream
    public void resetAudioStream() throws UnsupportedAudioFileException, IOException,
                                            LineUnavailableException 
    {
        audioInputStream = AudioSystem.getAudioInputStream(
        new File(filePath).getAbsoluteFile());
        clip.open(audioInputStream);
        clip.loop(Clip.LOOP_CONTINUOUSLY);
    }

}
```

在上面的程序中，我们使用了**音频输入流**，这是 Java 中的一个类，将音频文件作为一个流来读取。就像每一个 java 流一样，如果它要被再次使用，它必须被重置。

*   要暂停播放，我们必须停止播放器并将当前帧存储在一个对象中。以便在恢复时我们可以使用它。当恢复的时候，我们只需要从我们离开的最后一个位置重新开始比赛。
    clip.getMicrosecondPosition()方法返回音频的当前位置，clip.setMicrosecondPosition(长位置)设置音频的当前位置。
*   To stop the playback, you must have to close the clip otherwise it will remain open. I have also used clip.loop(Clip.LOOP_CONTINOUSLY) for testing. Because wav files are generally small so I have played mine in a loop.

    **要点:**

    1.  退出程序前，请始终关闭打开的流和资源。
    2.  在再次播放之前，您必须停止剪辑。所以保持适当的检查。
    3.  如果要再次使用音频输入流，必须将其重置。

    本文由**维沙尔·加尔格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
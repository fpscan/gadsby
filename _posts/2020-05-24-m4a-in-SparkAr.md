---
toc: false
layout: post
description: I got this when I started using github.
categories: [how-to, social]
title: How to convert and use .m4a files for SparkAR
---
# Audio files are tricky with Spark AR

There aren't lots of options for adding audio to your Spark AR Studio effects. It supports `.m4a` but you can't use a simple converted file. You need to have `mono` not `stereo` file. So what you can do is simple, you can use simple, free and open-source software called `Audacity`. So you can convert your `.mp3` or anyother audio file to `.m4a` with `mono`. [Download the Audacity software by clicking this whole sentence](https://www.audacityteam.org/download/). 

After the download it may ask you to locate `avformat-55.dll` this probable mean that you used `portable` version instead full installation. So you can go to this [download page](https://lame.buanzo.org/#lamewindl) and download **FFmpeg RECOMMENDED ZIP OPTION:** then you can unzip the file and you will have the `avformat-55.dll` which is a part of `ffmpeg` then locate it.


## How to convert the file to .m4a in corect way

You can check Spark AR documentation by going [here](https://sparkar.facebook.com/ar-studio/learn/documentation/docs/audio/) but one thing I am pretty sure you can't use every audio file. It has to be `Mono` .m4a file.

- Open Audacity then open your file by going `Open > your file`
*You will have your file listed on front of you*
- Then you need to Split to Mono
![This is how you can do](/images/audacity-ss1.png)
- Then remove second part which is right track with clicking `x` right next to file name
![This is how you can do](/images/audacity-ss2.png)
- Now you have to change PCM(*Pulse-code modulation*) to 16-bit by clicking the file name `Format > 16-bit PCM`
![This is how you can do](/images/audacity-ss3.png)
- Your audio file usually in 44100hz but in case it's not, you have to change it to;
![This is how you can do](/images/audacity-ss4.png)
- From now you can safely export by `File > Export > Export as WAV` change save as type to `.m4a` and quality usually same so if you think it has less quality you can export with higher quality option.

Now you can import your audio file into Spark AR scene.
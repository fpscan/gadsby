---
toc: false
layout: post
description: You can add the intro multiple files.
categories: [how-to, video]
title: How to add intro to multiple videos
image: images/th/batch-editing-ffmpeg-th.png
---
# FFmpeg and simple .bat file let you add your intros to videos.

There may be more than one way to achieve this, and it can be divided into paid or non-paid or fast or compatibility.What can we do? We can add intro to the beginning of more than one video using **FFmpeg**. For this we need FFmpeg and a smooth folder structure so we can work more efficiently.

## Folder Structure

Why is this important? Because working in a tidy environment is critical to efficiency and success. So the Folder Structure should be like this;

```
input(folder) > the videos we have will store here
output(folder) > the videos we will get with intro file will be there
intro(video file)
run.bat > the script we will use
```
So this how it suppose to look;

![Folder structure](/images/batch-editing-ffmpeg.png)

## Script

First you need to have [FFmpeg](https://www.ffmpeg.org/download.html) and you need to add into your path in order to use it globally. 

### How to do that?
 1. Unzip the FFmpeg to your C: drive.
 2. Then there will be `bin` folder, copy the folder path
 3. `Right Click to Computer > Properties > Advanced System Settings > Environment Variables > System Variables > Edit` then Add `C:\ffmpeg\bin` to this list 

Make a file as `run.bat` then right click and edit with [Sublime Text](https://www.sublimetext.com/3) or any other capable software or save it as `.txt` and edit with notepad then you can change extension back to `.bat` file.

```bash
SET RESOLUTION="1920:1080" 
SET INPUT_FOLDER="input"
SET INTRO="intro.mov"
SET OUTPUT_FOLDER="output"

for %%a in ("%INPUT_FOLDER%\*.*") do ffmpeg -i %INTRO% -i "%%a" -filter_complex "[0:v]scale=%RESOLUTION%:force_original_aspect_ratio=1,pad=%RESOLUTION%:(ow-iw)/2:(oh-ih)/2[v0]; [1:v]scale=%RESOLUTION%:force_original_aspect_ratio=1,pad=%RESOLUTION%:(ow-iw)/2:(oh-ih)/2[v1]; [v0][0:a][v1][1:a]concat=n=2:v=1:a=1[v][a]" -map [v] -map [a] "%OUTPUT_FOLDER%\%%~na.mp4"
```
### So what it does?

`SET RESOLUTION="1920:1080"` is force the resolution 1080p

`SET INPUT_FOLDER="input"` is the locate the place for your input folder

`SET INTRO="intro.mov"` is the intro file _you can change file name and extension based on what you have_

`SET OUTPUT_FOLDER="output` this is the folder for output files
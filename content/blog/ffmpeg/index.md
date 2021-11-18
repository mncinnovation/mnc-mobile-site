---
title: "FFMPEG"
description: "Introducing FFMPEG — by Bayu Wijaya Permana Putra."
lead: "Introducing FFMPEG, leading multimedia framework — by Bayu."
date: 2020-04-16T16:19:42+07:00
lastmod: 2020-04-16T16:19:42+07:00
draft: false
weight: 50
images: ["say-hello-to-doks.png"]
contributors: ["Bayu Wijaya Permana Putra"]
---
### Introduction
Today we often meet the media especially on social media (tiktok, instagram, facebook) that have video editor feature.

FFMPEG is an multimedia framework to record, convert and stream video and audio files, it supports nearly every digital format and codec known, it’s available on most operating systems and platforms it is a powerful command-line tool written in C and Assembly by Fabrice Bellard.

### Command
We can use command line to do various audio, video transcoding and conversion operations. 

We are now going to see some important and useful FFmpeg commands.

#### 1. Getting audio/video file information
To display the details of a media file, run:<br/>

```$ ffmpeg -i video.mp4```
Sample output:
```
ffmpeg version n4.1.3 Copyright (c) 2000-2019 the FFmpeg developers
built with gcc 8.2.1 (GCC) 20181127
configuration: --prefix=/usr --disable-debug --disable-static --disable-stripping --enable-fontconfig --enable-gmp --enable-gnutls --enable-gpl --enable-ladspa --enable-libaom --enable-libass --enable-libbluray --enable-libdrm --enable-libfreetype --enable-libfribidi --enable-libgsm --enable-libiec61883 --enable-libjack --enable-libmodplug --enable-libmp3lame --enable-libopencore_amrnb --enable-libopencore_amrwb --enable-libopenjpeg --enable-libopus --enable-libpulse --enable-libsoxr --enable-libspeex --enable-libssh --enable-libtheora --enable-libv4l2 --enable-libvidstab --enable-libvorbis --enable-libvpx --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxcb --enable-libxml2 --enable-libxvid --enable-nvdec --enable-nvenc --enable-omx --enable-shared --enable-version3
libavutil 56. 22.100 / 56. 22.100
libavcodec 58. 35.100 / 58. 35.100
libavformat 58. 20.100 / 58. 20.100
libavdevice 58. 5.100 / 58. 5.100
libavfilter 7. 40.101 / 7. 40.101
libswscale 5. 3.100 / 5. 3.100
libswresample 3. 3.100 / 3. 3.100
libpostproc 55. 3.100 / 55. 3.100
Input #0, mov,mp4,m4a,3gp,3g2,mj2, from 'video.mp4':
Metadata:
major_brand : isom
minor_version : 512
compatible_brands: isomiso2avc1mp41
encoder : Lavf58.20.100
Duration: 00:00:28.79, start: 0.000000, bitrate: 454 kb/s
Stream #0:0(und): Video: h264 (High) (avc1 / 0x31637661), yuv420p(tv, smpte170m/bt470bg/smpte170m), 1920x1080 [SAR 1:1 DAR 16:9], 318 kb/s, 30 fps, 30 tbr, 15360 tbn, 60 tbc (default)
Metadata:
handler_name : ISO Media file produced by Google Inc. Created on: 04/08/2019.
Stream #0:1(eng): Audio: aac (LC) (mp4a / 0x6134706D), 44100 Hz, stereo, fltp, 128 kb/s (default)
Metadata:
handler_name : ISO Media file produced by Google Inc. Created on: 04/08/2019.
At least one output file must be specified
```

#### 2. Converting video files to different formats
Since FFmpeg is a feature-rich and powerful audio and video converter, so It's possible to convert media files between different formats. Say for example, to convert mp4 file to avi file, run:<br/>
```$ ffmpeg -i video.mp4 video.avi```

Similarly, you can convert media files to any format of your choice.

For example, to convert youtube flv format videos to mpeg format, run:<br/>
```$ ffmpeg -i video.flv video.mpeg```
If you want to preserve the quality of your source video file, use '-qscale 0' parameter:<br/>
```$ ffmpeg -i input.webm -qscale 0 output.mp4```
To check list of supported formats by FFmpeg, run:<br/>
```$ ffmpeg -formats```

#### 3. Converting video files to audio files
To convert a video file to audio file, just specify the output format as .mp3, or .ogg, or any other audio formats.

The above command will convert input.mp4 video file to output.mp3 audio file.<br/>
```$ ffmpeg -i input.mp4 -vn output.mp3```

Also, you can use various audio transcoding options to the output file as shown below.<br/>
```$ ffmpeg -i input.mp4 -vn -ar 44100 -ac 2 -ab 320k -f mp3 output.mp3```<br/>

Here,
- -vn - Indicates that we have disabled video recording in the output file.
- -ar - Set the audio frequency of the output file. The common values used are  22050, 44100, 48000 Hz.
- -ac - Set the number of audio channels.
- -ab - Indicates the audio bitrate.
- -f - Output file format. In our case, it's mp3 format.

#### 4. 


### Pros of using FFmpeg
- It is also highly portable.
- It is profoundly valuable for the transcoding of all kinds of multimedia files into a single common format.
- You don’t need heavy Third-party VideoEditors like Adobe Premiere Pro, Filmora for small editing tasks.

### Cons of using FFmpeg
- It’s difficult for beginners to use and implement.
- It takes some time to process. We don’t get results in a second or two.
- The official documentation is quite confusing and it’s not beginner-friendly.
- APK size becomes very large. The FFmpeg libraries alone will use 30-70MB depending upon the libraries you are including.
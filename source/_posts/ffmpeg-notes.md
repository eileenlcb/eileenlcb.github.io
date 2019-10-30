---
title: FFmpeg notes
date: 2019-10-30 21:09:59
tags: 学习
---

这里记录一些常用的命令，以方便事后查阅。
由于项目需要常常用到ffmpeg，需要将video转化为图片，处理后再拼接回视频，因此用到了ffmpeg。

1.视频转化为图片（默认帧率）
`ffmpeg -i 01.flv %6d.png`
2.视频截取（ffmpeg -ss 00:00:47 -t 20 -accurate_seek -i 01.flv -codec copy  -avoid_negative_ts 1 test.flv包含起始时间、时长、源文件、输出文件）
`ffmpeg -ss 00:00:47 -t 20 -accurate_seek -i 01.flv -codec copy  -avoid_negative_ts 1 test.flv`
3.图片拼接
``
---
layout: default
nav_order: 3
title: ar_face
has_children: true
---


# AR_face

## 使用技术
方法定义
人脸关键点检测有2种使用方法，一种是输入一张静态图片进行检测，另一种是通过摄像头实时检测。

1. 静态图片检测
通过 VKSession.detectFace 接口 输入一张图像，算法检测到图像中的人脸，然后通过 VKSession.on 接口 输出人脸位置坐标、106个关键点坐标以及人脸在三维坐标系中的旋转角度。

2. 通过摄像头实时检测
算法实时检测相机中的人脸，通过 VKSession.on 接口 实时输出人脸位置坐标、106个关键点坐标以及人脸在三维坐标系中的旋转角度。
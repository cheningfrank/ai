---
layout: default
nav_order: 4
title: ar_hands
has_children: true
---


# AR_hands

## Hand检测
VisionKit从基础库 2.28.0版本开始提供hand检测能力。从 微信>=8.1.0 版本开始提供人手3D关键点检测，作为Hand检测的扩展能力接口。

### 方法定义
hand检测有2种使用方法，一种是输入一张静态图片进行检测，另一种是通过摄像头实时检测。

1. 静态图片检测
通过 VKSession.detectHand 接口 输入一张图像，算法检测到图像中的手势，然后通过 VKSession.on 接口 输出获取的手势关键点信息。

2. 通过摄像头实时检测
算法实时检测相机中的手势姿态，通过 VKSession.on 接口 实时输出检测到的手势关键点。
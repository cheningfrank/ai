---
layout: default
nav_order: 5
title: ar_distance
has_children: true
---


# AR_distance

## 方法定义
2D/3D Marker AR能力，能够识别预先设定的目标物体(定义为Marker，包括2D平面物体和3D物体），进行视觉跟踪与定位，通过在目标物体周围渲染虚拟物体，从而实现AR功能。

## 方法区别
2D Marker，仅适用于平面类物体，用户上传一张平面物体的俯视图像作为目标物体，算法运行时识别该平面物品，并渲染出相关虚拟物体。2D Marker可以理解为特殊的3D Marker。
3D Marker，相比于2D Marker，能够识别3D物体，不局限与平面物体，具有更广的使用范围，算法运行前，需要手动制作3D Marker的识别目标文件（.map文件），然后算法运行时载入该文件用于识别。
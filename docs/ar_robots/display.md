---
layout: default
title: display
nav_order: 1
parent: ar_robots
---
{: .warning }
> 机器人各项参数代码设置

```js
const cameraBusiness = require('../../utils/cameraBusiness.js')
// 画布id
const canvasId = 'canvas1';
// 机器人模型，带动画。
const robotUrl = 'https://m.sanyue.red/demo/gltf/robot.glb';
// webgl画面录制器的帧数
const recorderFPS = 30
// webgl画面录制器的最长录制时间（单位：秒）
const recorderMaxTime = 5
// 画布组件
var canvas1;
// webgl画面录制器
var recorder;
// 是否在录制webgl画面
var isRecording = false
```


{: .note }
> Image of our ar_robots' function

![our image of our robots](../../assets/ar_robots.jpg)



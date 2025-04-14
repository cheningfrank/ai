---
title: ar_robots
nav_order: 2
layout: default
has_children: true
---
# AR_robots
## 使用技术
6DoF-平面 AR能力
方法定义
6DoF-平面AR能力，提供基础AR功能，提供旋转和平移6自由度的定位功能。

包括 V1 和 V2 两种适用不同场景的算法，两种平面AR能力各有优劣，用户根据适用场景及产品需求，自行判断调用接口类型，具体介绍如下：

V1平面接口，适用于用户在平面场景下，例如桌面，地面，泛平面场景，放置虚拟物体，不提供真实世界距离。用户放置物体时，手机相机倾斜向下对着目标平面点击即可，具有广泛的机型支持。
V2平面接口，提供真实物理距离的ar定位功能，提供平面识别功能，用户在平面范围点击放置虚拟物体的功能，具有有限的支持机型。
能力扩展
在 V2 平面基础上，可以通过配置开启多种扩展能力，比如：

marker 识别能力，即平面空间下多个不同识别目标的识别。
虚实遮挡的能力，即虚拟物体和真实世界的交互遮挡能力。
更多使用效果与开关配置细节，可以参考 平面AR能力扩展
## 具体代码实现

{: .warning } 
> 获取3d模型

```js
onReady() {
    console.log('onReady')

    // 获取小程序右上角胶囊按钮的坐标，用作自定义导航栏。
    const menuButton = wx.getMenuButtonBoundingClientRect()

    this.setData({
      // 胶囊按钮与手机屏幕顶端的间距
      menuButtonTop: menuButton.top,
      // 胶囊按钮的高度
      menuButtonHeight: menuButton.height,
    })

    // 获取画布组件
    wx.createSelectorQuery()
      .select('#' + canvasId)
      .node()
      .exec(res => {
        // 画布组件
        canvas1 = res[0].node
        // 启动AR会话
        cameraBusiness.initEnvironment(canvas1)
        // 加载3D模型
        cameraBusiness.loadModel(robotUrl, function (model, animations) {
          // 创建AR的坐标系
          cameraBusiness.initWorldTrack(model)
          // 加载3D模型的动画
          cameraBusiness.createAnimation(model, animations, 'Dance')
        })
        // webgl画面录制器
        recorder = wx.createMediaRecorder(canvas1, {
          fps: recorderFPS,
        })

      })


  },
```
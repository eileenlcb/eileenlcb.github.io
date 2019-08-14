---
title: Unity学习总结——AngryBirds
date: 2019-08-08 21:30:55
tags: 学习
---

1）不同物体之间可以设置层级关系。选中物体后，在Sorting layer中，可以调整Order layer。
2）添加joint2d组件后，会自动添加rigidbody2d组件。
3) onMouseDown和onMouseUp为鼠标函数。特别的，在获得鼠标位置时，需要有鼠标位置的世界坐标和屏幕坐标的转化。
4）rigidbody2d开启Kinematic后，便忽视了物理引擎（牛顿定律），不进行物理计算。
5）Unity中有三种碰撞检测，onCollisionenter和ontriggerenter及射线检测。如果是onCollisionenter，需让物体同时挂载在collider和rigidbody上；ontriggerenter只要有物体挂载了rigidbody就可以，但是要开启istrigger。
6）可直接用print输出。【看到任务16中途】
7）2d游戏中，如果贴图出现前后遮挡时，可以通过Z轴关系或者layer层来进行处理。
渲染层级为【1】camera层：先绘制depth低的；【2】同一个camera中，按layer绘制；【3】同一个layer层，按layer的order绘制。统一都是大的挡住小的。
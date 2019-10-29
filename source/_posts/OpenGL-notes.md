---
title: "OpenGL notes"
date: 2019-10-30 01:24:45
tags: 学习
---

`gl_Position`为内建的GLSL变量，它是顶点着色器的裁剪空间输出位置向量。如果你想在屏幕上显示任何东西，在顶点着色器中设置gl_Position是必须的步骤。
`gl_VertexID`指gl_VertexID是一个在OpenGL中是一个内置的变量，每个顶点运行它时它们的`gl_VertexID`都不一样。我们利用这样的特点，将此作一个索引，得到不同的gl_Position，用以传入下一阶段——栅格化（Rasterize），这样一个三角形就得以显示出来了。

```
"#version 410 core                                                    "
	"                                                                 "
	"void main(void)                                                  "
	"{                                                                "
	"    const vec4 vertices[] = vec4[](vec4( 0.25, -0.25, 0.5, 1.0), "
	"                                   vec4(-0.25, -0.25, 0.5, 1.0), "
	"                                   vec4( 0.25,  0.25, 0.5, 1.0));"
	"                                                                 "
	"    gl_Position = vertices[gl_VertexID];					      "
	"}                                                                "
```

`gl_FragCoord`为gl_FragCoord的x和y分量是片段的窗口空间(Window-space)坐标，其原点为窗口的左下角。

`glVertexAttrib4fv`指定通用顶点属性的值。
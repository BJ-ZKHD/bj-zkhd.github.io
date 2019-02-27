---
layout:     post
title:      Mission Planner 二次开发
subtitle:   环境搭建和关键模块解析
date:       2019-02-27
author:     Shawn@bj-zkhd
header-img: img/zkhd-bz-5.jpg
catalog: true
tags:
    - MissionPlanner
---

# 背景介绍
Mission Planner作为当年3DR的遗产，一个功能强大的地面站软件，和飞控一起收编在Ardupilot门下。和其齐名的还有个叫QGC-QGroundContrl的地面站。都是在github上开源的项目。

Mission Planner基于.net开发，理论上只能在windows上使用，不过近年来.net尝试在跨平台支持，如支持linux下运行，不过距离windows的表现还有一定距离，目前还是在windows上使用比较靠谱，对于抱着学习或使用的目的的话，支持windows就足够了。

Mission Planner基于C#开发，一个介于C/C++和JAVA之间的优秀的语言，使用宇宙第一的IDE - Visual Studio开发，并且保持更新。开发用到了一些第三方组建，如：OpenGL用于呈现3D模型；Zedgraph用于绘图等等。都是些比较小而灵活的组件，有更好的组件提供方案也方便替换。这一点 QGC区别较大，QGC为了保持良好的可以移植性采用了QT作为基本开发框架，可以方便的在Windows、Andriod和Linux上编译运行，但是需要QT开发框架和熟悉其内部组件，使得系统可读性变差，不适合入门学习者。 通讯上两者都采用了Mavlink协议，兼容性较好，对应复杂都也较高，可扩展性很强。

Mission Planner项目共由47个左右的大小工程组成，代码看似庞大，实际上结构比较清晰，可阅读行很强，也很适合改造。

总之，比较适合飞控开发、调试和地面站学习。

# 源码下载

[Mission Planner 源码](Planner]https://github.com/ArduPilot/MissionPlanner)

[QGC 源码](https://github.com/mavlink/qgroundcontrol)

# 开发环境搭建
1. 基本工具和安装，仔细阅读 Mission Planner源码工程的readme即可。即：安装VS2017 Community 版，只要按提示注册一个微软账号，并且登陆即可免费使用。足够我们开发调试这个项目了(^_^ 吐个槽，微软这几年云化之后为了推广自家账号不遗余力:)。
2. 打上好各种依赖的.net 包。或者打开工程的时候，VS也会提示安装。 这个过程都要在线安装，比较大。
2. 另外需要下载个 net standard 安装一下，否则，编译可能编译不过。
3. 按照好全部编译即可生成可执行程序。


---
published: false
layout: post
title: "Swin Transformer论文解析"
categories: 我的AI新书
date: 2023-09-21 00:00:00 +0800
excerpt: "Swin Transformer论文解析"
---

论文标题：Swin:Hierarchical Vision Transformer using Shifted Windows
出自：微软亚洲研究院
荣誉：2021年最佳论文

**前提**
Vit的成功证明了Transformer能够在CV界大展拳脚。  

Swin的初衷是让Vit也像CNN一样具有多个Block的层级概念，具有多尺度的能力。  

**摘要**
Swin定位：一种新的Vision Transformer，用于计算机视觉任务的通用骨干网络，类似Resnet。  

背景：Vit直接从NLP应用到CV上面临两个挑战：
1.图像上会有不同大小尺寸的物体，也就是多尺度问题
2.图像尺寸太大，计算效率问题，后续要么用特征图作为输入，要么patch，要么划分成小窗口，在小窗口内计算注意力，分而治之。  


基于这两个挑战，Swin Transformer出现了。

他有两个特点：一个是层级式，另一个是shift window。


shift window的好处：注意力在窗口内计算，提升计算效率，shift操作能够让相邻窗口进行交互，实现全局建模能力。  

层级的好处：多尺度信息。

**引言**

两个事：
Swin想要干什么？
Answer：Transformer可以作为一个通用的骨干网络 ，不光是分类，检测，分割都可以。

对于视觉任务，多尺度至关重要。  
在CNN中，目标检测领域解决多尺度应用最广的是FPN，Feature Pyramid Network。
在CNN中，分割领域解决多尺度的方法是UNet中的skip connection。  以及PSP，ASPP，空洞卷积。

原始Vit单一16倍下采样不适合密集预测。注意力始终在全局图像上建模。  可以利用图像的局部性。

patch merging多尺寸特征。  



Swin的贡献

